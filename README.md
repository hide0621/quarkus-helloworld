# quarkusでプロジェクトを作る際のコマンド

例えば、言語は`Kotlin`、ビルドツールは`gradle`といった条件でquarkusプロジェクトを作りたいなら、

`quarkus create app quarkus-helloworld --kotlin --gradle`

このようにコマンドを書き、実行する

以下、解説すると...

・　`quarkus create app`：Quarkusフレームワークを使用して新しいアプリケーションを作成するコマンドです。

・　`quarkus-helloworld`：新しく作成されるアプリケーションの名前です。

・　`--kotlin`：このオプションを指定すると、アプリケーションのプログラミング言語として`Kotlin`が選択されます。

・　`--gradle`：このオプションを指定すると、ビルドツールとして`Gradle`が選択されます。

上記のような意味を持つコマンドになる。

# 開発モードで実行

以下のコマンドによりアプリケーションを開発モードで実行できる。

これにより、ライブコーディングが可能になる。

`./gradlew quarkusDev`

---

# quarkus-helloworld

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./gradlew quarkusDev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./gradlew build
```
It produces the `quarkus-run.jar` file in the `build/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `build/quarkus-app/lib/` directory.

The application is now runnable using `java -jar build/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:
```shell script
./gradlew build -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar build/*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./gradlew build -Dquarkus.package.type=native
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./build/quarkus-helloworld-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/gradle-tooling.

## Related Guides

- Kotlin ([guide](https://quarkus.io/guides/kotlin)): Write your services in Kotlin

## Provided Code

### RESTEasy Reactive

Easily start your Reactive RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)
