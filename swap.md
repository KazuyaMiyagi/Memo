# swap

```
# swap領域がないことを確認
# swapon -s
Filename                                Type            Size    Used    Priority

# swapファイルを作成
# dd if=/dev/zero of=/swapfile bs=1M count=1024
1024+0 records in
1024+0 records out
1073741824 bytes (1.1 GB) copied, 7.27087 s, 148 MB/s

# swapファイルのパーミッションを変更
# chmod 600 /swapfile

# swap領域を作成
# /sbin/mkswap /swapfile
mkswap: /swapfile: warning: don't erase bootbits sectors
        on whole disk. Use -f to force.
Setting up swapspace version 1, size = 1048572 KiB
no label, UUID=966fdfd1-8d62-4e85-9b5d-c11d4e47b897

# swap領域を有効化
# swapon /swapfile

# swap領域が有効化されていることを確認
# swapon -s
Filename                                Type            Size    Used    Priority
/swapfile                               file            1048572 0       -1

# メモリのスワップ領域のサイズを確認
# free -m
             total       used       free     shared    buffers     cached
Mem:          3829       2081       1747          0         74       1706
-/+ buffers/cache:        300       3528
Swap:         1023          0       1023

# fstab にswapファイルの設定を追加
# echo "/swapfile swap swap defaults 0 0" >> /etc/fstab

# fstab の内容を即時有効化
# swapon -a

# swap領域が有効化されていることを確認
# swapon -s
Filename                                Type            Size    Used    Priority
/swapfile                               file            1048572 0       -1

# メモリのスワップ領域のサイズを確認
# free -m
             total       used       free     shared    buffers     cached
Mem:          3829       2081       1747          0         74       1706
-/+ buffers/cache:        300       3528
Swap:         1023          0       1023
```
