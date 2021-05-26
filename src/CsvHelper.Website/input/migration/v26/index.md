# Migrating from version 25 to 26

## Delegates

All delegates args objects have their `init` accessor removed. 
Constructor parameters are used instead.

**BadDataFoundArgs**

```cs
// v26
var args = new BadDataFoundArgs
{
	Field = field,
	RawRecord = rawRecord,
	Context = context,
};

// v27
var args = new BadDataRoundArgs(field, rawRecord, context);
```

**ConvertFromStringArgs**

```cs
// v26
var args = new ConvertFromStringArgs
{
	Row = row,
};

// v27
var args = new ConvertFromStringArgs(row);
```

**ConvertToStringArgs**
```cs
// v26
var args = new ConvertToStringArgs
{
	Value = value,
};

// v27
var args = new ConvertToStringArgs(value);
```

**GetConstructorArgs**
```cs
// v26
var args = new GetConstructorArgs
{
	ClassType = type,
};

// v27
var args = new GetConstructorArgs(type);
```

**GetDynamicPropertyNameArgs**
```cs
// v26
var args = new GetDynamicPropertyNameArgs
{
	FieldIndex = index,
	Context = context,
};

// v27
var args = new GetDynamicPropertyNameArgs(index, context);
```

**HeaderValidatedArgs**
```cs
// v26
var args = new HeaderValidatedArgs
{
	InvalidHeaders = headers,
	Context = context,
};

// v27
var args = new HeaderValidatedArgs(headers, context);
```

**MissingFieldFoundArgs**
```cs
// v26
var args = new MissingFieldFoundArgs
{
	HeaderNames = headerNames,
	Index = index,
	Context = context,
};

// v27
var args = new MissingFieldFoundArgs(headerNames, index, context);
```

**PrepareHeaderForMatchArgs**
```cs
// v26
var args = new PrepareHeaderForMatchArgs
{
	Header = header,
	FieldIndex = fieldIndex,
};

// v27
var args = new PrepareHeaderForMatchArgs(header, fieldIndex);
```

## IParserConfiguration

- Added property `bool ExceptionMessagesContainRawData { get; }`.

Any class that implements `IParserConfiguration` will need these changes
applied to it.

## IWriterConfiguration

- Added property `bool ExceptionMessagesContainRawData { get; }`.

Any class that implements `IParserConfiguration` will need these changes
applied to it.


