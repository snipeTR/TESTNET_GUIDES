# Linux Sunucuda Otomatik Program Yeniden Başlatma

Bu rehberde, Linux sunucuda `goracle docker-start` isimli programın otomatik olarak yeniden başlatılmasını sağlamak için gerekli adımlar açıklanmaktadır. Bu rehber, hiç Linux bilmeyenler için hazırlanmıştır.

## Gereksinimler

- Linux sunucu (root erişimine sahip)
- SSH yazılımı
- tmux
- nano

## Adım 1: Sistem Güncelleme

Sunucunuza SSH yazılımı kullanarak root erişimi sağlayın ve aşağıdaki komutları çalıştırın:

```apt update && apt upgrade -y```


Bu, sunucunuzdaki tüm paketleri günceller.

## Adım 2: Gerekli Araçların Kurulumu

Bu adımda, `tmux` ve `nano` araçlarını yükleyeceğiz. Bunları tek bir komutla yükleyebilirsiniz:

```apt install tmux nano -y```


## Adım 3: Tmux Kullanımı

Tmux, birden fazla sanal konsolu aynı anda yönetmenizi sağlayan bir araçtır. Bu adımda, tmux'u başlatıp ekranı dikey olarak ikiye böleceğiz.

```tmux```

Ekranı yatay olarak ikiye bölmek için aşağıdaki tuş kombinasyonu kullanın.
(ctrl ile b ye aynı anda basıp, tuşu bırakıp % karakterine basmanız lazım.)
```Ctrl-b %```


## Adım 4: Otomatik Program Yeniden Başlatma

Bu adımda, `goracle docker-start` isimli programın otomatik olarak yeniden başlatılmasını sağlayacağız. Bunu yapmak için, aşağıdaki komutları kullanarak sağ panoya geçin:

(ctrl ile b ye aynı anda basıp, tuşu bırakıp sağ ok tuşuna basmanız lazım.)
```Ctrl-b →```

Panoya geçtiğinizde, aşağıdaki komutu çalıştırın:

```while true; do goracle docker-start; sleep 10; echo "Press Ctrl-C to stop the script"; done```


Bu komut, `goracle docker-start` programını sonsuz bir döngü içinde çalıştırır ve program herhangi bir nedenle çöktüğünde, 10 saniye bekleyerek yeniden başlatır. Ayrıca, program yeniden başlatılırken "Press Ctrl-C to stop the script" mesajını ekrana yazar.

## Sonuç

Artık `goracle docker-start` programı otomatik olarak yeniden başlatılacaktır ve program herhangi bir nedenle çöktüğünde, 10 saniye bekleyerek yeniden başlatılacaktır. Bu, sunucunuzdaki önemli programların sürekli olarak çalışmasını sağlayacaktır.
