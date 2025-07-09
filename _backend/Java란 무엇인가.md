---
title: 
date: 2015-08-14
tags:
  - Java
category: Java
---
Java는 1995년 James Gosling 의 주도로 새롭게 등장한 **객체 지향 프로그래밍 언어**입니다.  
지금은 Oracle이 유지·관리하고 있으며, **모바일(Android)**, **웹 서버**, **클라우드**, **게임**, **데스크톱 애플리케이션**까지 다양한 분야에서 사용되고 있습니다.

이 문서에서는 Java의 기본 개념부터 [JDK](#jdk-java-development-kit), [JRE](#jre-java-runtime-environment), [JVM](#jvm-java-virtual-machine), [javac](#javac-java-compiler), [Java 라이브러리](#java-라이브러리), [클래스 로더](#클래스-로더-class-loader)까지 자바 생태계를 구성하는 핵심 요소들을 정리합니다.
## ☕ Java란?

Java는 한 번 작성하면 여러 플랫폼에서 실행할 수 있는 **플랫폼 독립적인 언어**입니다.  
사람이 작성한 소스 코드를 [javac](#javac-java-compiler)로 컴파일하면 `.class`라는 **바이트코드**가 생성되고, 이 바이트코드는 [JVM](#jvm-java-virtual-machine) 위에서 실행됩니다.
## 🌟 Java의 주요 특징

| 특징             | 설명                                                          |
| -------------- | ----------------------------------------------------------- |
| ✅ 객체 지향        | 클래스와 객체 중심의 구조로 구성되어 있음                                     |
| ✅ 플랫폼 독립       | 한 번 컴파일하면 JVM이 설치된 어느 OS에서나 실행 가능                           |
| ✅ 메모리 자동 관리    | JVM 내부의 Garbage Collector가 자동으로 정리                          |
| ✅ 풍부한 표준 라이브러리 | 다양한 [Java 라이브러리](#java-라이브러리) 제공 (`java.util`, `java.io` 등) |
| ✅ 보안성          | [클래스 로더](#클래스-로더-class-loader)와 런타임 검사로 안전성 확보              |
| ✅ 다중 쓰레드 지원    | JVM 기반으로 멀티쓰레드 프로그래밍에 최적화                                   |

> Java의 대표 철학: **Write Once, Run Anywhere**

---

## 🔧 JDK (Java Development Kit)

Java 애플리케이션을 **개발**할 때 필요한 모든 도구의 모음입니다.

**포함 요소**:
- [JRE](#jre-java-runtime-environment)
- [javac](#javac-java-compiler) (컴파일러)
- javadoc, jar, jdb 등 개발 유틸리티

> 개발자라면 **JDK만 설치하면 OK!**

---

## 🎯 JRE (Java Runtime Environment)

Java 프로그램을 **실행**하는 데 필요한 환경입니다.

**포함 요소**:
- [JVM](#jvm-java-virtual-machine)
- [Java 라이브러리](#java-라이브러리) (기본 API)

> 실행만 한다면 **JRE로 충분**합니다. 개발자는 JRE가 포함된 JDK를 씁니다.

---

## 🚀 JVM (Java Virtual Machine)

Java **바이트코드(`.class`)를 읽고 실행**하는 가상의 머신입니다.

**포함 요소**:
- [클래스 로더](#클래스-로더-class-loader)
- 메모리 구조, GC, 실행 엔진 등

**역할**:
- 플랫폼 독립성 제공 (`Write once, run anywhere`)
- 바이트코드를 각 OS 네이티브 코드로 변환하여 실행

---

## 🛠️ javac (Java Compiler)

`.java` → `.class` 파일로 변환해 주는 컴파일러입니다.

```bash
javac HelloWorld.java
# → HelloWorld.class 생성
```

이 후 `.class`는 [JVM](#jvm-java-virtual-machine)이 실행합니다.

## 📚 Java 라이브러리

표준 API 클래스들의 모임입니다. 예:

- `String`, `ArrayList`, `HashMap`, `Scanner`, `Math`, `File` 등
    

**라이브러리 구조**:

- 대부분 `java.*`, `javax.*`, `javafx.*` 패키지로 제공됩니다.
    
- [JRE](#jre-java-runtime-environment)에 포함되어 있어 사용자가 따로 설치할 필요 없음
    

---

## 📥 클래스 로더 (Class Loader)

`.class` 파일을 **JVM 내부 메모리로 자동 로딩**하는 역할을 합니다.

**종류**:

- `Bootstrap ClassLoader` – Java 기본 API 로딩
    
- `Extension ClassLoader` – 확장 라이브러리
    
- `Application ClassLoader` – 애플리케이션 클래스

## 🌐 전체 흐름 요약

```plaintext
[개발자 작성]
   ↓ javac (컴파일)
Hello.java → Hello.class
   ↓ 클래스 로더
   ↓ JVM (실행)
[Java 라이브러리 + JVM 구성 요소와 함께 프로그램 실행]

```

## 🧩 포함 관계 비교

|구성 요소|포함 요소|
|---|---|
|**JDK**|JRE + javac + 개발 도구|
|**JRE**|JVM + Java 라이브러리|
|**JVM**|클래스 로더 + GC + 실행 엔진|

---

## ✨ Kotlin과 비교: Kotlin 생태계와 Java의 공통점

Kotlin도 JVM 기반 언어로, Java와 **호환되면서도 더 간결한 구조**를 제공합니다.  
JetBrains가 개발했으며, Android 및 JVM 개발에 널리 사용됩니다.

> 참고: [Kotlin Notion 정리 보기](https://teamsparta.notion.site/Kotlin-8-22b2dc3ef51480a5af24ed53213aa13c)

---

## 📎 참고 자료

- [Oracle 공식 JDK 다운로드](https://www.oracle.com/java/technologies/javase-downloads.html)
    
- [Java SE API 문서](https://docs.oracle.com/en/java/javase/)
    
- [Kotlin 공식 문서](https://kotlinlang.org/)


---


