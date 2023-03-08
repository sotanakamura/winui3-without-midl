# WinUI 3 with C++ and XAML but without MIDL
You can define WinUI 3 UIs with XAML. Classes reffered in XAML should be Windows runtime classes which you define with MIDL. Creating Windows Runtime classes is a little bit hard. This repositry provides information aboud how to define UIs with XAML but without MIDL.

## Define UIs in C++
See [WinUI 3 in C++ Without XAML](https://github.com/sotanakamura/winui3-without-xaml)

## Define UIs in XAML instead of C++ code

1. Add MainPage.xaml file to define UIs.

    ```xaml
    // MainPage.xaml
    <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation">
        <StackPanel HorizontalAlignment="Center" VerticalAlignment="Center">
            <TextBlock>Hello World!</TextBlock>
        </StackPanel>
    </Window>
    ```

1. Load XAML file and assign it as a UIElement object.

    ```cpp
    window = Window();
    Application::LoadComponent(window, Uri(L"ms-appx:///MainPage.xaml"));
    ```

## Build and run
You can see a window displaying "Hello World!"

## Note
You need to implement event hundlers and binding in C++ code. If you want to do it in XAML, you need to create Windows Runtime class with MIDL. 
