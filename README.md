# ie-Array.find
Adds support for the Array.prototype.find() function in Internet Explorer

In order to add the functionality of array.find() to internet explorer, add this to the top of your script:
```
if(Array.prototype.find == null){
	Array.prototype.find = function(callback, thisArg){
		for(var i = 0; i < this.length; i++){
			if(callback.call(thisArg || window, this[i], i, this))
				return this[i];
		}
		return undefined;
	};
}
```
