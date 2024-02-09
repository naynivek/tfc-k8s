FROM public.ecr.aws/amazonlinux/amazonlinux:latest as cowsaybuilder
WORKDIR /app

RUN dnf install --assumeyes cowsay
RUN cowsay -f dragon Welcome to nginx!  > index.html

FROM nginx:latest

COPY default.conf /etc/nginx/conf.d/default.conf
COPY --from=cowsaybuilder /app/index.html /usr/share/nginx/html/dragons-warning/index.html

EXPOSE 80
