# Use the capbuilder for the first stage build
FROM stanisorre/capui5tools:1.0.0-20220322111145_538673c as capbuild
#Base version
ENV VERSION 1.0.0
# Create app directory, in which the CAP service is built
WORKDIR /app
# Set to production mode
ENV NODE_ENV=production
# Copy source
COPY components .
# build app
RUN ["cds", "build"]
# Switch to db build
WORKDIR /app/gen/db
# Install db dependencies
RUN npm install
# Run build
CMD [ "npm", "start", "--", "--exit" ]
