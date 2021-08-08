# Stack and Heap

## Stack

## Heap


# Parameters

### Passing  arguments by  value
By default, arguments in C# are passed by value.

### The `ref` modifier
To pass by reference, C# provides the `ref` parameter modifier.

### The `out` modifier
An `out` argument is like a `ref` argument, except it:

- Need not be assigned before going into the function
- Must be assigned before it comes out of the function

```
class Example{

	static void Split(string name, out string firstName, out string lastName)
	{
		int index = name.LastIndexOf(' ');
		firstName = name.Substring(0,index);
		lastName = name.Substring(index+1);
	
	}

}

```

Like a `ref` parameter, an `out` parameter is passed by ==reference==.


### The  `params` modifier
The `params` parameter modifier may be specified on the last parameter of a method so that the method accepts any number of arguments of a particular type. The parameter type must be declared as an array.

```
//code ommited

static int Sum( params int[] numbers){
	//code
	
	return sum;
}

// invoking the method

int sumOfNumbers = Sum(1,2,3,4);

```