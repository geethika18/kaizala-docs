```typescript
enum KASFormPropertyType {
  // Any text is allowed as the metadata value
  Text = 0,
  // Only numbers are allowed as the metadata value
  Numeric = 1,
  // Location type as the metadata value
  Location = 2,
  // Date time as the metadata value
  DateTime = 3,
  // Stringify value of array of strings as the metadata value
  Array = 4,
  // Attachment path as the metadata value
  Attachment = 5,
  // Stringify value of set (unique list) of strings as the metadata value
  Set = 6,
  // Stringify value of list of KASAttachment as metadata value
  AttachmentList = 7
}
```
