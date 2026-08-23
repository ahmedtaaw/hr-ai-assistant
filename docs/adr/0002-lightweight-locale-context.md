# 0002: Lightweight locale context over i18n library
Decision: Custom LocaleProvider toggling dir + a strings object.
Because: MVP has ~4 screens, mocked data, 1-month solo constraint — a full i18n library is over-engineering for this scope.
Alternative considered: next-intl — better if the product grows into many pages/strings later.