# Linux

## ls

* `ls -l` Liste şeklinde chmod, boyut vs gösterir
* `ls -a` Gizli dosyalarıda gösterir.
* `ls -h` Boyutu mb cinsinden gösterir.
* `ls -lhS` Boyuta göre sıralar.
* `ls -lht` Zaman göre sıralar.

## cat

* `cat production.log | grep 2014-02-22 | more`
* `cat production.log | grep 2014-02-22 | grep xxx.xx.185.119` tarih ve ip ile ara
* `cat production.log | grep 2014-02-22 | grep -v INFO` Infoları gösterme


## tail

* `tail -f production.log`
* `tail -n 300`

## Kaynaklar

* `free`                  # ram bilgisi
* `cat /proc/cpuinfo`     # cpu bilgisi
