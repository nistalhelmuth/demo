ARG         TAG_VERSION
FROM        neowu/jre:${TAG_VERSION}
MAINTAINER  rewardsweb
EXPOSE      8443
RUN         addgroup --gid 1000 --system app && adduser --system --no-create-home --ingroup app --uid 1000 app
RUN         apk add --no-cache gcompat
USER        1000
