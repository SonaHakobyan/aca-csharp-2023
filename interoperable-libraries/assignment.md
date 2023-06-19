# Interoperable Libraries Assignment

## Overview

Create two libraries written in different .net-compliant languages ( Visual Basic and C# ) that interact with each other.

## Geometry Library (Visual Basic)

Develop a Geometry DLL that contains Point and Line types written in Visual Basic.

```vb
Namespace Geometry
    Public Structure Point
        Public X As Integer
        Public Y As Integer

        Public Sub New(ByVal x As Integer, ByVal y As Integer)
            Me.X = x
            Me.Y = y
        End Sub
    End Structure
End Namespace

Namespace Geometry
    Public Class Line
        Public Property StartPoint As Point
        Public Property EndPoint As Point

        Public Sub New(ByVal startPoint As Point, ByVal endPoint As Point)
            Me.StartPoint = startPoint
            Me.EndPoint = endPoint
        End Sub
    End Class
End Namespace
```

Use Developer Command Prompt to compile Point.vb and Line.vb files into a single Geometry.dll using Visual Basic compiler (vbc.exe).


## Graphics Library (C#)

Develop a Graphics DLL that contains ColoredLine type, written in C#. 
ColoredLine class uses Line type from Geometry DLL. It has DrawLine public method that draws the colored line in Console.

```cs
using System;
		using Geometry;

		namespace Graphics
		{
			public class ColoredLine
			{
				private readonly Line line;
				private readonly ConsoleColor color;

				public ColoredLine(Line line, ConsoleColor color)
				{
					this.line = line;
					this.color = color;
				}

				public void DrawLine()
				{
					var deltaX = this.line.EndPoint.X - this.line.StartPoint.X;
					var deltaY = this.line.StartPoint.Y - this.line.StartPoint.Y;

					var slope = (double)deltaY / deltaX;
					var currentY = (double)this.line.StartPoint.Y;

					Console.ForegroundColor = this.color;

					for (var x = this.line.StartPoint.X; x <= this.line.EndPoint.X; x++)
					{
						var roundedY = (int)Math.Round(currentY);
						Console.SetCursorPosition(x, roundedY);
						Console.Write("■");

						currentY += slope;
					}
				}
			}
		}
```

Use Developer Command Prompt to compile ColoredLine.cs file and referenced Geometry.dll into a single Graphics.dll using C# compiler (csc.exe).
Make sure that the integration between the DLLs is correct and that the necessary dependencies are properly resolved.
	

## Console Application (C#)
Develop a simple C# console application that demonstrates the usage of the types from the Geometry and Graphics DLLs.
The application should create an instance of ColoredLine type and perform DrawLine operation on it.
Verify that the final C# file can be successfully compiled and executed.

Refer to Microsoft Documentation for compiling commands.
Feel free to make any changes to examples and try to integrate types written in any other .net-compliant language into your project.