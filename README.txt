Why compositor ?
Display Manager Vs Window Manager ?
###################################

A. Display Manager
==================
Some times it's also referred to as login manager, its the GUI that is displayed at the end of bootup process (in the place of shell of a headless server). They are fairly lighweight and some time writtern in BASH.

Functionality:
1. Provide login screen
2. On successfull login turns control over to window manager

Example
=======
GDM (GNOME display manager),
KDM (KDE display manager),
SSDM (Simple desktop display manager)

Window Manager
==============
A window manager (WM) is system software that controls the placement and appearance of windows within a windowing system in a graphical user interface (GUI).
It can be part of a desktop environment (DE) or be used standalone.
Variants:
1. Stacking window manager
2. Tiling window manager
3. Dynamic window managers

Example
=======
Compiz, IceWM, Xfwm

X11 Vs Wayland ?

FB Vs DRM Vs V4L2 ?

Buffer management in various components ?

Selecting the right Graphics and Video API
##########################################
1. FB device
2. DRM (direct rendering manager)
3. V4L2


COMPILATION
===========
export PKG_CONFIG_PATH=/home/skamath/compositor/out/share/pkgconfig:$PKG_CONFIG_PATH

~/compositor/dev/meson/meson.py --reconfigure \
        -Dbackend-default=x11 \
        -Dbackend-drm=false \
        -Dbackend-drm-screencast-vaapi=false \
        -Dbackend-fbdev=false \
        -Dbackend-headless=false \
        -Dbackend-rdp=false \
        -Dbackend-wayland=false \
        -Dimage-webp=false \
        -Dsystemd=false \
        -Dlauncher-logind=false \
        -Dxwayland=false \
        -Dcolor-management-colord=false \
        -Dcolor-management-lcms=false \
        -Dremoting=false \
        -Ddemo-clients=false \
        -Dsimple-clients=egl \
        -Dsimple-dmabuf-drm="" \
        -Dtest-junit-xml=false \
        -Dprefix=$HOME/compositor/out ..

ERROR
=====
./weston-launch: Permission denied. You should either:
 - enable systemd session support for weston-launch.
 - or add yourself to the 'weston-launch' group.

