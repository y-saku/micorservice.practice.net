FROM mcr.microsoft.com/dotnet/sdk:6.0
WORKDIR /app

###MyOrigin####
# 開発で使用するツールをインストール
# RUN apt update && apt upgrade
# RUN apt install -y procps \
#                    iputils-ping
## SSLエラー対策
RUN dotnet dev-certs https --clean
RUN dotnet dev-certs https --trust
# dotnet tools install
# RUN dotnet tool update --global PowerShell
# ENV PATH $PATH:/root/.dotnet/tools
##############

ENV ASPNETCORE_URLS http://+:80
#ENV HOST=0.0.0.0
EXPOSE 80
COPY ./app/* .
RUN dotnet restore
# ENTRYPOINT ["dotnet", "run"]