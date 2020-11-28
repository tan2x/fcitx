Fcitx 4 is under maintainence Mode now, so no new issue and PR should be created.

Please give fcitx 5 a try if possible. If you're experiencing problem, you can
reach out mail list (fcitx[at]googlegroups.com) or IRC (fcitx[at]freenode) for help.

Please read http://fcitx-im.org for further help.

See COPYING and COPYING.LIBS for License information.

***

Here is a patch for AlpineLinux  made by [linuxboy](https://www.zhihu.com/people/nniixx) that abandons BACKTRAC

```
apk add musl-libintl
apk add gettext-dev
mkdir build
cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr \
	-DSYSCONFDIR=/etc \
	-DENABLE_GTK3_IM_MODULE=ON \
	-DENABLE_X11=ON \
	-DENABLE_GTK2_IM_MODULE=OFF \
	-DENABLE_CAIRO=ON \
	-DENABLE_DBUS=ON \
	-DENABLE_LIBXML2=ON \
	-DENABLE_GIR=ON \
	-DENABLE_GLIB2=ON \
	-DENABLE_OPENCC=ON \
	-DENABLE_ENCHANT=OFF \
	-DENABLE_PRESAGE=OFF \
	-DENABLE_QT=OFF 
make 
make install   # root 
gtk-query-immodules-3.0 > /etd/gtk-3.0/gtk.immodules # root
export LANG=zh_CN.UTF-8
export XMODIFIERS=@im=fcitx
export GTK_IM_MODULE=fcitx
```

And set your X file
