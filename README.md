# piecewise-db-dump
https://github.com/opentechinstitute/piecewise

load database:

    gunzip -c dump.tar.gz | pg_restore -U postgres -d piecewise -O --clean

export database:

    pg_dump -Ft -U postgres piecewise --clean -t results -t district_statistics -t block_statistics | gzip > dump.tar.gz
