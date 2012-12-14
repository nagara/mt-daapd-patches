patches for mt-daapd
========
mt-daapd を快適に使うための patch repository です。

mt-daapd_r1696_cp932.patch 
--------
mt-daapd rev1696 を CP932 (≒Shift-JIS) の ID3 タグ対応にするパッチです。[かずー氏のパッチ](http://www.kzsoft.to/~kazu/mt-daapd/ "iTunesサーバ(mt-daapd/Firefly)日本語スマートプレイリスト対応パッチ")をベースに [MEDIA STREET さんが手を入れた](http://media.st/blog/2011/10/build-firefly-mt-daapd-win32/ "Firefly(mt-daapd)のWindows版を自力ビルドしてみる")パッチを rev1696 向けに書き直したものです。

mt-daapd の src ディレクトリで使ってください。

    $ patch < mt-daapd_r1696_cp932.patch

mt-daapd_r1696_albumartist.patch
--------
mt-daapd rev1696 を Album Artist 対応にするパッチです。[MEDIA STEETさん](http://media.st/ "MEDIA STREET")の [Firefly(mt-daapd)をアルバムアーティスト対応にする](http://media.st/blog/2011/10/firefly-mt-daapd-albumartist/ "Firefly(mt-daapd)をアルバムアーティスト対応にする")パッチを rev1696 向けに書き直したものです。

mt-daapd rev1696 は、データベースに album_artist フィールドを持っています。orchestra フィールドの使用はやめて album_artist フィールドを使っています。

mt-daapd の src ディレクトリで -p0 付きで使ってください。

    $ patch -p0 < mt-daapd_r1696_albumartist.patch

mt-daapd_r1696_scan-mp3_albumartist.patch
--------
mt-daapd rev1696 を Album Artist 対応にするパッチ、その2です。mp3 ファイルの TPE2 フレームをデータベースの orchestra フィールドではなく、album_artist フィールドに保存するようにします。mt-daapd_r1696_cp932.patch を適用した後に使用してください。

mt-daapd の src ディレクトリで使ってください。

    $ patch < mt-daapd_r1696_scan-mp3_albumartist.patch

mt-daapd_r1737_aac-albumartist.patch (おまけ)
--------
[mt-daapd rev1737 stable-aspl-free branche](http://mt-daapd.svn.sourceforge.net/viewvc/mt-daapd/branches/stable-aspl-free/ "Index of /branches/stable-aspl-free") で aac ファイルも Album Artist タグを取得するようにするパッチです。単独でも使えますが、[MEDIA STEETさん](http://media.st/ "MEDIA STREET")の [Firefly(mt-daapd)をアルバムアーティスト対応にする](http://media.st/blog/2011/10/firefly-mt-daapd-albumartist/ "Firefly(mt-daapd)をアルバムアーティスト対応にする")パッチと一緒に使わないとあんま意味がありません。

AAC ファイルの aART タグを orchestra フィールドに保存します。

mt-daapd の src ディレクトリで使ってください。

    $ patch < mt-daapd_r1737_aac-albumartist.patch

[MEDIA STEETさんの記事](http://media.st/blog/2011/10/firefly-mt-daapd-albumartist/ "Firefly(mt-daapd)をアルバムアーティスト対応にする")で紹介されている [mt-daapd rev1737 stable-aspl-free branche](http://mt-daapd.svn.sourceforge.net/viewvc/mt-daapd/branches/stable-aspl-free/ "Index of /branches/stable-aspl-free") は src ディレクトリの中身が実質 rev1589 なので rev1696 を使うことをオススメします。
