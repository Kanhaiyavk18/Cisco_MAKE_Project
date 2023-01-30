https://buildgrid.build/index.html
https://buildgrid.gitlab.io/recc/index.html
.venv/bin/bgd server start server.yml
.venv/bin/bgd server start cas_ram.yml
.venv/bin/bgd server start cas_disk.yml
.venv/bin/bgd bot --remote=http://sjc-ads-2513:50051 --remote-cas=http://sjc-ads-2513:50052 --instance-name=buildgrid -vvv host-tools

RECC
source /auto/andatc/independent/shellrc-files/current/rc/.bashrc.build.bglr
export PATH=/auto/andatc/linux/recc/build/bin:$PATH

export RECC_SERVER=bgl-ads-1754:50051
export RECC_CAS_SERVER=bgl-ads-1754:50052
export RECC_INSTANCE=main
export RECC_LOG_LEVEL=debug
export RECC_PROJECT_ROOT=$(pwd
export RECC_SKIP_CACHE=0
unset RECC_SKIP_CACHE
export ARCH=x86n


export RECC_SERVER=bgl-ads-5645:50051
export RECC_CAS_SERVER=bgl-ads-5645:50052
export RECC_INSTANCE=main
export RECC_LOG_LEVEL=debug
export RECC_PROJECT_ROOT=$(pwd
export RECC_SKIP_CACHE=0
unset RECC_SKIP_CACHE

Time:-
bt=`date +'%s'`
make CC='recc gcc'
et=`date +'%s'`
dur=$(expr $et - $bt )
echo "
rm -r -f image_m9700_sf3ek9_kickstart 
gmake RECC=1 -k  -j96 images/final/m9700_sf3ek9_kickstart
et=`date +'%s'`
dur=$(expr $et - $bt )
echo "Building recc took $dur "
