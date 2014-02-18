A thread safe sql-tokenizer for MySQL Proxy & OneProxy
==========================================================

The original sql-tokenizer in MySQL Proxy 0.8.x is not thread safe, 
it's protected by a global static mutex, which caused really back performance for OneProxy.

So I modify the sql-tokenizer.l to sql-tokenizer2.l, with higher version of flex,
It could produce a thread safe sql-tokenizer without the global static mutex required.

./ylwrap sql-tokenizer2.l lex.yy.c sql-tokenizer2.c -- flex
