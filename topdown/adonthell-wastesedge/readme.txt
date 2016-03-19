author: Waste's Edge Team
license: GPL2
origin: https://github.com/ksterker/wastesedge
        http://adonthell.nongnu.org/
        https://sourceforge.net/projects/adonthell/
        http://savannah.nongnu.org/projects/adonthell/


"There's a script in v0.4 that can extract the graphics and
save them as PNGs (test/convert_graphics.py). However, I think it does
not yet recognize the character format." --Kai Sterker (http://adonthell-artwork.nongnu.narkive.com/Lc1goUzu/jelom-rasgar-sprite-test)


following script was used for dumping graphics

//first folder should be processed with following commands
//for i in *.pnm; do convert "$i" "$i.png"; done
//for i in *.img; do mv "$i" "$i.gz"; gunzip "$i.gz"; done
//for i in *.anim; do mv "$i" "$i.gz"; gunzip "$i.gz"; done
//for i in *.mchar; do mv "$i" "$i.gz"; gunzip "$i.gz"; done
//for i in *.mobj; do mv "$i" "$i.gz"; gunzip "$i.gz"; done

save_png W H Bs Dst =
| Gfx = gfx W H
| Gfx.clear{#FF000000} // transparent
| for Y H: for X W:
  | R = Bs^pop
  | G = Bs^pop
  | B = Bs^pop
  | Gfx.set{X Y rgb{R G B}}
| Gfx.save{Dst}

Folder = '/Users/nikita/Downloads/1/mapobjects/0'

for File Folder.items.keep{?url.2><img}
| Bs = "[Folder]/[File]".get
| case Bs [2/W.u2 2/H.u2 @Bs]
  | save_png W H Bs "[Folder]/[File].png"

for File Folder.items.keep{?url.2><anim}
| Bs = "[Folder]/[File]".get
| case Bs [8/Dummy 2/N.u2 2/W.u2 2/H.u2 @Bs]
  | Sz = W*H*3
  | for I N
    | B = Bs.take{Sz}
    | Bs <= Bs.drop{Sz}
    | X,Y = Bs.take{4}.group{2}{?u2}
    | Bs <= Bs.drop{4}
    | save_png W H B "[Folder]/[File]-[I].png"

for File Folder.items.keep{?url.2><mchar}
| Bs = "[Folder]/[File]".get
| L = Bs.size
| I = 0
| while Bs.size > 16
  | if Bs.take{4}.u4><#001E0014 then //all frames are 20x30
     | W = Bs.take{2}.u2
     | Bs <= Bs.drop{2}
     | H = Bs.take{2}.u2
     | Bs <= Bs.drop{2}
     //| say (L-Bs.size).x
     | save_png W H Bs "[Folder]/[File]-["[I]".pad{-2 '0'}].png"
     | Bs <= Bs.drop{W*H*3}
     | !I+1
    else
     | pop Bs

for File Folder.items.keep{?url.2><mobj}
| Bs = "[Folder]/[File]".get
| L = Bs.size
| Bs <= Bs.drop{3}
| NN = Bs.take{2}.u2
| Bs <= Bs.drop{2}
| if NN >< 1 then
   | Bs <= Bs.drop{8}
   | N = Bs.take{2}.u2
   | Bs <= Bs.drop{2}
   | for I N
     | W = Bs.take{2}.u2
     | Bs <= Bs.drop{2}
     | H = Bs.take{2}.u2
     | Bs <= Bs.drop{2}
     | when W > 200 or H > 200:
       | say "bad WxH: [W]x[H]"
       | halt
     | save_png W H Bs "[Folder]/[File]-["[I]".pad{-2 '0'}].png"
     | Bs <= Bs.drop{W*H*3}
  else
   | Bs <= Bs.drop{8}
   | for J NN
     | N = Bs.take{2}.u2
     | Bs <= Bs.drop{2}
     | for I N
       | W = Bs.take{2}.u2
       | Bs <= Bs.drop{2}
       | H = Bs.take{2}.u2
       | Bs <= Bs.drop{2}
       | say W,H
       | when W > 200 or H > 200:
         | say 'bad WxH'
         | _goto skip
       | save_png W H Bs "[Folder]/[File]-[J]-[I].png"
       | Bs <= Bs.drop{W*H*3+#16}
| _label skip