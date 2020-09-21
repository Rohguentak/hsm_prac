# hsm_prac
참고 https://whamcloud.github.io/Online-Help/docs/Config_and_using_HSM_6_0.html#6.3
iml에서 hsm agent 노드 추가하는 방법

     $root@mds2: lctl set_param mdt.<$FSNAME>-MDT0000.hsm_control=enabled
     mdt.lustre-MDT0000.hsm_control=enabled
     $root@mds2: lctl get_param mdt.<$FSNAME>-MDT0000.hsm_control
     mdt.lustre-MDT0000.hsm_control=enabled
     

     $root@hsm-agent: lhsmtool_posix --hsm_root /archive --daemon /lustre //데몬이 실행되어야 copytool 사용 가능
     $root@client1234 #: lfs hsm_archive /mnt/lustre/path/to/big_file
     $root@client1234 #: lfs hsm_release /mnt/lustre/path/to/big_file
     
     
# robinhood
참고 https://github.com/cea-hpc/robinhood/wiki/v3_lhsm_tuto 

    $lctl --device <fsname>-MDT0000 changelog_register
