## Async ##

This module is responsible for executing a sequence of asynchronous/concurrent code.

**Usage:** Include the content of `async.pluri` in your program, and then call the module.

**Example:** The code below creates two concurrent tasks, but the third task will wait for the completion of the previous two

    "async" {
    	
        "javascript" {
			console.log('First Task');

			var that = this;
			setTimeout(function(){
				that.done('');
			}, 3000)
		}

		"javascript" {
		    console.log('Second task, it is concurrent');

			var that = this;
			setTimeout(function(){
				that.done('');
			}, 1000)
		}
    }

    "javascript" {
    	console.log('Third task, waits for async completion');
    	this.done('');
    }



