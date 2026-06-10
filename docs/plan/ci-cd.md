# CI/CD - Building Book

## Pipeline de Integración Continua

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Java 25
        uses: actions/setup-java@v4
        with:
          java-version: '25'
          distribution: 'graalvm'

      - name: Compile
        run: ./gradlew build

      - name: Generate diagrams
        run: plantuml -tsvg docs/**/*.puml

      - name: Test
        run: ./gradlew test

  native:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Java 25
        uses: actions/setup-java@v4
        with:
          java-version: '25'
          distribution: 'graalvm'

      - name: Build Native Image
        run: ./gradlew nativeCompile

      - name: Upload binaries
        uses: actions/upload-artifact@v4
        with:
          name: bbook-binaries
          path: cli/build/native/*