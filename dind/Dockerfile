FROM docker:dind

# docker-compose インストール
RUN apk update && apk add docker-compose git openjdk8

# mbe-local-env取得 (TODO:あとでsshで取るよう修正)
RUN git clone https://git.dmm.com/mbe-yggdrasill/mbe-local-env.git

# 作業ディレクトリ設定
WORKDIR /mbe-local-env

# dmm-member-flywayを取得 (TODO:あとでsshで取るよう修正)
RUN mkdir -p mbe-migration-container/src
RUN git clone https://git.dmm.com/mbe-yggdrasill/dmm-member-flyway.git mbe-migration-container/src/dmm-member-flyway

# dmm-member-spring clone TODO:CircleCIでは checkoutで持ってくる。
RUN git clone https://git.dmm.com/mbe-yggdrasill/dmm-member-spring.git /dmm-member-spring

# 


# コンテナ実行シェル
# ※docker系の処理は、実際に起動するDockerデーモンを参照しないと実行できない。→ビルド、もできない。
#CMD docker-compose build
# コンテナ実行
#RUN docker-compose up -d mbe-mysql
#RUN docker-compose up -d account_migrate
#RUN docker-compose up -d account_test_migrate

#dev-jenkins...   ./gradlew -i -x purgeTestBuckets clean flushTestBuckets member-controllers:test
# build
#./gradle -i auth-controllers:localWar
#./gradle -i member-controllers:localWar
#./gradle -i guest-controllers:localWar

#test
#./gradle -i member-controllers:test
#./gradle -i auth-controllers:test
#./gradle -i guest-controllers:test
#./gradle -i cucumber:test
# パラメータ指定
#./gradlew -i auth-controllers:test --tests "com.dmm.member.app.test.controller.authentication.LoginAutomaticTest.testExpiredAutomaticAuthentication_newToken"

# Log path is /var/log/openapi/member/auth/



# dood方式ではdocker.sockをマウントする。
#-v /var/run/docker.sock:/var/run/docker.sock 
#-v $(which docker):/usr/bin/docker
