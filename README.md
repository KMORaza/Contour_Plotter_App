### Contour Plotter App
This is a desktop application that allows users to generate 3D contour plots based on mathematical expressions and visualize them in a separate window. Additionally, it provides functionality to save the generated plots as either PNG or can print it to PDF file.

#### Here are some calculations used:

Linespace: $x_i = a + i \cdot \frac{{b - a}}{{\text{{num}} - 1}}$ where $i=0,1,2,3,...,num-1$

Meshgrid: $x_{ij} = X_i, \quad y_{ij} = Y_j$ where $i$ and $j$ are indices of $X$ and $Y$

#### Functioning of the application:

START APP

FUNCTION Generate_Contour($X$,$Y$,Expression){

$X$
$Y$
$X$, $Y$ = Meshgrid($X$, $Y$)
$Z$ = Evaluate($X$,$Y$,Expression)
Plot=Create()
Projection="3D"
Plot 3D Contor
    add_colorbar(ax, contour_plot, label='Function Value')
    set_axes_labels(ax, variable_x, variable_y)
    set_plot_title(ax, '3D Contour')
    add_text_annotation(ax, expression.format(variable_x, variable_y))
    RETURN Plot

# Class for the Contour Plotter Application
CLASS ContourPlotApp:
    # Constructor
    FUNCTION __init__(self, root):
        initialize_main_window(root)

    # Method to generate and show the plot
    FUNCTION generate_plot():
        variable_x = get_user_input("Variable for x-axis:")
        variable_y = get_user_input("Variable for y-axis:")
        expression = get_user_input("Mathematical expression (use {} for variables):")
        IF variable_x AND variable_y AND expression:
            fig = generate_3d_contours(variable_x, variable_y, expression)
            show_plot(fig, variable_x, variable_y, expression)

    # Method to show the plot in a separate window
    FUNCTION show_plot(fig, variable_x, variable_y, expression):
        plot_window = create_new_window(title="3D Contour Plot")
        create_menu_bar(plot_window)
        create_file_menu(plot_window)
        create_gui_components(plot_window)

    # Method to save the plot as PNG
    FUNCTION save_plot_as_png(fig):
        file_path = ask_user_for_file_path(default_extension=".png", file_types=[("PNG files", "*.png")])
        IF file_path:
            save_figure_as_png(fig, file_path)
            show_success_message("Successfully saved!", "Plot saved as PNG file.")

    # Method to save the plot and function details as PDF
    FUNCTION save_plot_and_function_as_pdf(fig, variable_x, variable_y, expression):
        file_path = ask_user_for_file_path(default_extension=".pdf", file_types=[("PDF files", "*.pdf")])
        IF file_path:
            save_figure_and_function_as_pdf(fig, file_path, variable_x, variable_y, expression)
            show_success_message("Export successful!", "PDF file has been saved.")

# Main part of the script
IF __name__ == "__main__":
    root = create_main_tkinter_window()
    app = ContourPlotApp(root)
    start_main_tkinter_loop()

# End Contour Plotter
