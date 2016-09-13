### How to update the GS secret key
==============================================

```
cd /home/ubuntu/genomespace/gensecretkey
./gengssecretkey.sh
mv genomespace-secret.key ..
cd ..
cp genomespace-secret.key /root/genomespace
```

Finally, re-build the code
