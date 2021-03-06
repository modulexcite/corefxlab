# .NET Core Lab

This repo is for experimentation and exploring new ideas that may or may not make it into the main corefx repo.

Curently, this repo contains the following experimental components:

* **System.Text.Formatting**. 
System.Text.Formatting APIs are similar to the existing StringBuilder and TextWriter APIs. 
They are designed to format values into text streams and to build complex strings. 
But these APIs are optimized for creating text for the Web. 
They do formatting with minimum GC heap allocations (1/6 of allocations in some scenarios) and can format directly to UTF8 streams. 
This can result in significant performance wins for software that does a lot of text formatting for the Web, e.g. generating HTML, JSON, XML. 
See more information on this component and code samples at the [Wiki]: https://github.com/dotnet/corefxlab/wiki 

* **System.IO.FileSystem.Watcher.Polling**. 
.NET's FileSystemWatcher has low overhead, but it can miss some changes. This is acceptable in many scenarios, but in some, it night be not. This component, PollingWatcher, allows to monitory directory changes by polling, and so will never miss a change. It is optimized to minimize allocations, when no changes are detected. In fact, it does not allocate anything on the GC heap when there are no changes detected. 

More libraries are coming soon. Stay tuned!

[blog post]: http://blogs.msdn.com/b/dotnet/archive/2014/11/12/net-core-is-open-source.aspx

## Related Projects

For an overview of all the .NET related projects, have a look at the
[.NET home repository](https://github.com/Microsoft/dotnet).

## License

This project is licensed under the [MIT license](LICENSE).

## .NET Foundation

This project is a part of the [.NET Foundation].

[.NET Foundation]: http://www.dotnetfoundation.org/projects
[.NET Foundation forums]: http://forums.dotnetfoundation.org/

## Building and Testing

To find out how you can build and test .NET Core, see the [Developer Guide].

[Developer Guide]: https://github.com/dotnet/corefx/wiki/Developer-Guide
