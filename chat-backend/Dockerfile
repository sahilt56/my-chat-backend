# Alpine Linux ka naya version istemaal karein
FROM alpine:latest
# Migrations folder ko copy karo
COPY ./pb_migrations /pb/pb_migrations
# Kaam karne ke liye ek directory banayein
WORKDIR /pb

# PocketBase ka version set karein (aap ise badal sakte hain)
ARG PB_VERSION="0.22.18"

# PocketBase ko download aur unzip karein
ADD https://github.com/pocketbase/pocketbase/releases/download/v${PB_VERSION}/pocketbase_${PB_VERSION}_linux_amd64.zip .
RUN unzip pocketbase_*.zip

# Railway $PORT variable ka istemaal karke server ko start karein

CMD ["/bin/sh", "-c", "./pocketbase serve --http=0.0.0.0:$PORT --origins='https://my-chat-frontend-production.up.railway.app'"]



