FROM codesignal/ubuntu-base:v5.0

RUN add-apt-repository -y ppa:marutter/rrutter \
  && add-apt-repository -y ppa:marutter/c2d4u \
  && apt-get update \
  && apt-get install -y --no-install-recommends r-base \
  && apt-get install -y --no-install-recommends \
    r-cran-stringr \
    r-cran-jsonlite \
    r-cran-httr \
    r-cran-dplyr \
    r-cran-magrittr \
    r-cran-data.table \
    r-cran-futile.logger \
    r-cran-devtools \
  && rm -rf /var/lib/apt/lists/*

RUN Rscript -e "library(remotes); install_github('aryoda/tryCatchLog');"
