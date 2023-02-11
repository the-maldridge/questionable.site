FROM docker.io/library/alpine as build
WORKDIR /vdo
RUN wget -O /tmp/vdo.tar.gz https://github.com/steveseguin/vdo.ninja/archive/refs/tags/v22.9.tar.gz && \
    tar --strip-components=1 -zvxf /tmp/vdo.tar.gz -C /vdo

FROM docker.io/library/nginx
COPY --from=build /vdo /usr/share/nginx/html/
