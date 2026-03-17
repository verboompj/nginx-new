# ── Stage: serve with nginx ──────────────────────────────────────────────────
FROM nginx:1.27-alpine

# Remove the default nginx welcome page
RUN rm -rf /usr/share/nginx/html/*

# Copy our site content
COPY index.html /usr/share/nginx/html/index.html

# nginx listens on 80 by default
EXPOSE 80

# Healthcheck — ACI can use this to verify the container is alive
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
  CMD wget -qO- http://localhost/ || exit 1
