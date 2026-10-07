---
apple-notes-id: 3289F221-3492-4477-A04C-33FDADDC9B5C
---
Exceptions are objects of the Exception class or its subclasses. The raise method causes an exception to be raised. This interrupts the normal flow through the code. Instead, Ruby searches back through the call stack for code that says it can handle this exception.
Both methods and blocks of code wrapped between begin and end keywords intercept certain classes of exceptions using rescue clauses:

```
begin
content = load_blog_data(file_name)
rescue BlobDataNotFound
STDERR.puts "File #{file_name} not found"
rescue BlogDataFormatError
STDERR.puts "Invalid #{file_name}"
rescue Exception => err
STDERR.puts "General error loading #{file_name}: #{err.message}"

```
rescue clauses can be directly placed on the outermost level of a method definition without needing to enclose the contents in a begin/end block.
That concludes our brief introduction to control flow. At this point you have the basic building blocks for creating larger structures.