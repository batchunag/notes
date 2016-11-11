#CMDで実行する
nohup　R　--vanilla　--slave　< hoge.r >　hoge.txt
http://www014.upp.so-net.ne.jp/acremaker/u1.html

UNIX言語において、nohupというコマンドがログアウトしても実行し続けるようにするコマンドです。
--vanilla　：　Ｒを何のオブジェクトもない状態で起動する。
--save　：　--vanillaの逆で今までのオブジェクトを残したままＲを起動する。
--slave　：　標準出力への文字の出力を抑制します。

#Unicode
 Sys.getlocale()
 to check the locale