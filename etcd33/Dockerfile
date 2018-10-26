FROM alpine:latest
RUN mkdir -p /app/static/dist /app/conf
# COPY --from=backend /go/src/github.com/shiguanghuxian/etcd-manage/etcd-manage /app
# COPY --from=frontend /app/dist /app/static/dist
COPY ./etcd-manage /app
COPY static/dist /app/static/dist
COPY conf/config.default.ini /app/conf
EXPOSE 9090
WORKDIR /app
CMD ["./etcd-manage"]
