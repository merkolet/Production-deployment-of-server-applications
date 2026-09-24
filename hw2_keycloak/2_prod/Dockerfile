FROM quay.io/keycloak/keycloak:24.0 AS builder

# build-time опции вшиваются в сборку, поэтому start --optimized
# не пересобирает Keycloak при каждом запуске контейнера
ENV KC_DB=postgres
ENV KC_HEALTH_ENABLED=true

RUN /opt/keycloak/bin/kc.sh build


FROM quay.io/keycloak/keycloak:24.0

COPY --from=builder /opt/keycloak/ /opt/keycloak/

ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
CMD ["start", "--optimized"]
