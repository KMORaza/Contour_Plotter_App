### Contour Plotter App
This is a desktop application that allows users to generate 3D contour plots based on mathematical expressions and visualize them in a separate window. Additionally, it provides functionality to save the generated plots as either PNG or can print it to PDF file.

#### Here are some calculations used:

Linespace: $x_i = a + i \cdot \frac{{b - a}}{{\text{{num}} - 1}}$ where $i=0,1,2,3,...,num-1$

Meshgrid: $x_{ij} = X_i, \quad y_{ij} = Y_j$ where $i$ and $j$ are indices of $X$ and $Y$

#### Functioning of the application:

    START App
    FUNCTION Plot_Contour(X,Y,Expression){
        X,Y = Meshgrid(X,Y)
        Z = Evaluate(X,Y,Expression)
        Projection = "3D"
        Figure = Plot(X,Y,Z)
        RETURN Figure
    }
    INITIALIZE Main_Window
    FUNCTION Generate_Contour{
        X = Get input variable 
        Y = Get input variable
        Figure = Plot(X,Y,Z)
        DISPLAY Figure
    }
    FUNCTION Display(Figure, X, Y, Expression){
        Plot Window
    }
    FUNCTION Save{
        Extension = "PNG"
        File_Path = Ask User
        Save PNG
    }
    FUNCTION Export{
        Extension = "PDF"
        File_Path = Ask User
        Save PDF
    }
    END App

Please note this psedocode only demonstrates working of application in simpler way. Actual app is more complex and involves external libraries for computation and processing of contour plots
