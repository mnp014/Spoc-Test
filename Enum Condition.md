# Java
```
public enum AnEnum {
   A(true), B(false), C(false), D(true);

   AnEnum(boolean isError) {
       this.isError = isError
   }
}
```
---
# groovy
```
class AnEnumSpec extends Specification {

    def "has correct error status"() {
        expect:
        result == anEnum.isError

        where:
        anEnum   | result
        AnEnum.A | true
        AnEnum.B | false
        AnEnum.C | false
        AnEnum.D | true
    }
}
```
---
# JUnit
```
public class TestEnum {
    public String method(AnEnum anEnum) {
         if( anEnum.isError() ) {
              return "An Error";
         }
         return "Not An Error";
    }
}
```
