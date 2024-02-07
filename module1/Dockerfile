FROM public.ecr.aws/amazonlinux/amazonlinux:latest as cowsaybuilder
WORKDIR /app

RUN dnf install --assumeyes cowsay
RUN cowsay -f dragon The Winter is comming  > index.html

FROM nginx:latest

COPY --from=cowsaybuilder /app/index.html /usr/share/nginx/html/
EXPOSE 80
