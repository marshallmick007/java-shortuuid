# java-shortuuid
[![Build Status](https://travis-ci.org/hsingh/java-shortuuid.svg?branch=master)](https://travis-ci.org/hsingh/java-shortuuid)

A generator library for concise, unambiguous and URL-safe UUIDs

A Java library that generates concise, unambiguous, URL-safe UUIDs. Based on and compatible with the Python library [`shortuuid`](https://github.com/stochastic-technologies/shortuuid). Inspired by the Go [implementation](https://github.com/renstrom/shortuuid).

Often, one needs to use non-sequential IDs in places where users will see them, but the IDs must be as concise and easy to use as possible. shortuuid solves this problem by generating UUIDs using and then translating them to base57 using lowercase and uppercase letters and digits, and removing similar-looking characters such as `l`, `1`, `I`, `O` and `0`.

## Usage

```java
public String shortUuid() {
    ShortUuid.Builder builder = new ShortUuid.Builder();
    ShortUuid shortUuid = builder.build(UUID.randomUUID());
    
    return shortUuid.toString();
}

public UUID getUuid(String shortUuid) {
    ShortUuid.Builder builder = new ShortUuid.Builder();
 
    return UUID.fromString(builder.decode(shortUuid));
}
```

## License

MIT
