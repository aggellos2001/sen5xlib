# sen5xlib
> [!NOTE]  
> This project is not affiliated with Sensirion in any way shape or form!

This is the CGO wrapper that uses the [Sensirion Raspberry Pi I2C SEN5x Driver](https://github.com/Sensirion/raspberry-pi-i2c-sen5x).
You can inspect the [sen5x.go](sen5x.go) file to see what functions the wrapper implements.


## Installation
Since this is a go module you can add it to your Go project by running the usual command which will add the library
to your go.mod file.

```bash
go get github.com/aggellos2001/sen5xlib@latest
```

### Example
Reading and printing the serial number from the device:

```go
package yourpackagename

import (
	[...] // other import statements
	"github.com/aggellos2001/sen5xlib"
)

func main() {
	sen5xlib.InitializeHal()
	defer sen5xlib.FreeHal()
	
	serial, err := sen5xlib.ReadSerialNumber()
	if err != nil {
		log.Fatalln(err)
	}

	log.Println("serial number:", serial)
}
```


## Contributing
If you want to contribute to this project, feel free to open a pull request. 
I will be happy to review it. If you have any questions, feel free to open an issue 
(or a discussion) and make sure to follow the appropriate template.

