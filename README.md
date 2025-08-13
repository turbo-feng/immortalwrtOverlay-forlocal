# immortalwrtOverlay-forlocal
为immortalwrt24.10.2准备的ib-overlay本地化编译文件，只记录了我修改的文件和脚本，ImageBuilder工具包并不在其中.你可以把它当做模板,适当修改,就能定制属于自己的固件了

#操作步骤
```shell
wget --no-check-certificate https://downloads.immortalwrt.org/releases/24.10.2/targets/x86/64/immortalwrt-imagebuilder-24.10.2-x86-64.Linux-x86_64.tar.zst
tar --use-compress-program=unzstd -xvf immortalwrt-imagebuilder-24.10.2-x86-64.Linux-x86_64.tar.zst
mv immortalwrt-imagebuilder-24.10.2-x86-64.Linux-x86_64 immortalwrt-24.10.2 && cd immortalwrt-24.10.2

wget -O master.zip https://github.com/wukongdaily/ib-overlay/archive/refs/heads/master.zip
unzip master.zip -d tempdir
rm -f tempdir/*/.gitignore tempdir/*/README.md tempdir/*/LICENSE
mv tempdir/*/* ./
mv *.config .config / 2>/dev/null
rm -rf tempdir
```
