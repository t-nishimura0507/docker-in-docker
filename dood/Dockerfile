FROM docker:19.03.13-git

# docker-compose インストール
RUN apk update && apk add docker-compose

# mbe-local-env取得 (TODO:あとでsshで取るよう修正)
RUN git clone https://git.dmm.com/mbe-yggdrasill/mbe-local-env.git

# 作業ディレクトリ設定
WORKDIR /mbe-local-env

# dmm-member-flywayを取得 (TODO:あとでsshで取るよう修正)
RUN mkdir -p mbe-migration-container/src
RUN git clone https://git.dmm.com/mbe-yggdrasill/dmm-member-flyway.git mbe-migration-container/src/dmm-member-flyway

# コンテナ実行
# RUN docker-compose build
# RUN docker-compose up -d

# TODO:コンテナ起動確認
# - flyway起動確認

# TODO: Java環境構築
# TODO: WARファイルセット

#-v /var/run/docker.sock:/var/run/docker.sock 
#-v $(which docker):/usr/bin/docker
