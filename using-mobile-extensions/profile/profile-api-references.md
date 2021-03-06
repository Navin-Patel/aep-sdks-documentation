# Profile API References

## Update User Attributes

{% tabs %}
{% tab title="Android" %}
### **updateUserAttribute**

Allows you to create/update a batch of user profile attributes:

* If the attribute does not exist, it will be created.
* If the attribute exists, the value will be updated.
* A null attribute value removes the attribute.

#### **Syntax**

```java
public static void updateUserAttribute(String attributeName, 
                                       Object attributeValue)
```

#### **Example**

```java
UserProfile.updateUserAttribute("username", "Will Smith");
```

### updateUserAttributes

Sets the user profile attributes key and value.

Allows you to create/update a batch of user profile attributes:

* String, Integer, Boolean, Double, Array, Map are valid type of user profile attributes.
* We do not allow custom objects to be saved as a `UserProfile` attribute.
* If the attribute does not exist, it will be created.
* If the attribute already exists, then the value will be updated.
* A null attribute value will remove the attribute.

#### **Syntax**

```java
public static void updateUserAttributes(Map<String, Object> attributeMap)
```

#### **Example**

```java
HashMap<String, Object> profileMap = new HashMap<>();
profileMap.put("username","Will Smith");
profileMap.put("usertype","Actor");
UserProfile.updateUserAttributes(profileMap);
```
{% endtab %}

{% tab title="iOS" %}
### updateUserAttribute

Sets the user profile attributes key and value and allows you to create or update a user profile attribute.

Remember the following information:

* If the attribute does not exist, it will be created.
* If the attribute already exists, then the value will be updated.
* A null attribute value will remove the attribute.

#### **Syntax**

```java
+ (void) updateUserAttribute: (nonnull NSString*) attributeName withValue: (nullable NSString*) attributeValue;
```

#### **Examples**

Here is an example in Objective-C:

```text
[ACPUserProfile updateUserAttribute:@"username" withValue:@"Will Smith"];
```

Here is an example in Swift:

```java
ACPUserProfile.updateUserAttribute("username", withValue: "Will Smith");
updateUserAttributes

```

### updateUserAttributes

Sets the user profile attributes key and value.

Allows to create/update a batch of user profile attributes:

* String, Integer, Boolean, Double, Array, Map are valid type of user profile attributes.
* We do not allow custom objects to be saved as a `UserProfile` attribute.
* If the attribute already exists, then the value will be updated.
* If the attribute does not exist, it will be created.

A null attribute value will remove the attribute.

#### **Syntax**

```text
+ (void) updateUserAttributes: (nonnull NSDictionary*) attributeMap
```

#### **Examples**

Here is an example in Objective-C:

```objectivec
NSMutableDictionary *profileMap = [NSMutableDictionary dictionary];
[profileMap setObject:@"username" forKey:@"will_smith"];
[profileMap setObject:@"usertype" forKey:@"Actor"];
[ACPUserProfile updateUserAttributes:profileMap];
```

Here is an example in Swift:

```swift
var profileMap = [AnyHashable: Any]()
profileMap["username"] = "will_smith"
profileMap["usertype"] = "Actor"
ACPUserProfile.updateUserAttributes(profileMap)
```
{% endtab %}
{% endtabs %}

## **Remove User Attributes**

Removes the given attribute name.

{% tabs %}
{% tab title="Android" %}
### **removeUserAttribute**

#### **Syntax**

```java
public static void removeUserAttribute(String attributeName)
```

#### **Example**

```java
UserProfile.removeUserAttribute("itemsAddedToCart");
```
{% endtab %}

{% tab title="iOS" %}
### removeUserAttribute

Removes the user profile attribute for the given key.

#### **Syntax**

```objectivec
+ (void) removeUserAttribute: (nonnull NSString*) key
```

#### **Examples**

Here is an example in Objective-C:

```objectivec
[ACPUserProfile removeUserAttribute:@"itemsAddedToCart"];
```

Here is an example in Swift:

```swift
ACPUserProfile.removeUserAttribute("itemsAddedToCart");
```
{% endtab %}
{% endtabs %}

