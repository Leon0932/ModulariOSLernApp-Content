# Learn SwiftUI

## Table of contents

1. [Beginner](#level-beginner)
      1. [Module 11: Introduction to SwiftUI](#module-11-introduction-to-swiftui)
         1. [Introduction](#introduction)
         2. [Declarative Syntax](#declarative-syntax)
         3. [VStack](#vstack)
         4. [HStack](#hstack)
         5. [ZStack](#zstack)
      2. [Module 12: State Management in SwiftUI](#module-12-state-management-in-swiftui)
         1. [State](#state)
         2. [Binding](#binding)
         3. [StateObject](#stateobject)
         4. [ObservedObject](#observedobject)
         5. [EnvironmentObject](#environmentobject)
2. [Intermediate](#level-intermediate)
      1. [Module 13: Components in SwiftUI](#module-13-components-in-swiftui)
         1. [Button Part I](#button-part-i)
         2. [Button Part II](#button-part-ii)
         3. [Button Part III](#button-part-iii)
         4. [TextField](#textfield)
         5. [Slider](#slider)
         6. [Toggle](#toggle)
         7. [System Images](#system-images)
      2. [Module 14: Navigation and Views](#module-14-navigation-and-views)
         1. [Navigation](#navigation)
         2. [TabView](#tabview)
3. [Advanced](#level-advanced)
      1. [Module 15: Advanced SwiftUI-Lectures](#module-15-advanced-swiftui-lectures)
         1. [Rotation Effect](#rotation-effect)
         2. [Scale Effects](#scale-effects)

### Level Beginner

#### Module 11: Introduction to SwiftUI

##### Introduction

SwiftUI helps you build great-looking apps across all Apple platforms with the power of Swift — and surprisingly little code. You can bring even better experiences to everyone, on any Apple device, using just one set of tools and APIs.

[SwiftUI Documentation](https://developer.apple.com/xcode/swiftui/)

##### Declarative Syntax

SwiftUI uses a declarative syntax, so you can simply state what your user interface should do. For example, you can write that you want a list of items consisting of text fields, then describe alignment, font, and color for each field. Your code is simpler and easier to read than ever before, saving you time and maintenance.

The following example displays a Text of "Hello World" with a font size of 32 and color red:

```swift
struct TextView: View {
    var body: some View {
        Text("Hello World")
            .font(.system(size: 32))
            .foregroundColor(.red)
    }
}
```
##### VStack

A view that arranges its subviews in a vertical line.

The following example shows a simple vertical stack of 10 text views, with a spacing of 10 and an alignment of `leading`:

```swift
struct VStackView: View {
    var body: some View {
        VStack(
                alignment: .leading,
                spacing: 10
            ) {
                ForEach(
                    1...10,
                    id: \.self
                ) {
                    Text("Item \($0)")
                }
            }
    }
}
```

[SwiftUI VStack Documentation](https://developer.apple.com/documentation/swiftui/vstack)

##### HStack

A view that arranges its subviews in a horizontal line.

The following example shows a simple horizontal stack of five text views, with a spacing of 5 and an alignment of `top`:

```swift
struct HStackView: View {
    var body: some View {
        HStack(
                alignment: .top,
                spacing: 10
            ) {
                ForEach(
                    1...5,
                    id: \.self
                ) {
                    Text("Item \($0)")
                }
            }
    }
}
```

[SwiftUI HStack Documentation](https://developer.apple.com/documentation/swiftui/hstack)

##### ZStack

The `ZStack` assigns each successive subview a higher z-axis value than the one before it, meaning later subviews appear “on top” of earlier ones.

The following example uses a `ZStack` to overlay a white "Center" text on top of a blue circle with a width and height of 100 points:

```swift
struct ZStackView: View {
    var body: some View {
        ZStack {
            Circle()
                .fill(Color.blue)
                .frame(width: 100, height: 100)
            Text("Center")
                .foregroundColor(.white)
        }
    }
}
```

[SwiftUI ZStack Documentation](https://developer.apple.com/documentation/swiftui/zstack)


#### Module 12: State Management in SwiftUI

##### State

A property wrapper type that can read and write a value managed by SwiftUI.

Use state as the single source of truth for a given value type that you store in a view hierarchy. Create a state value in a `View` by applying the `@State` attribute to a property declaration and providing an initial value. Declare state as private to prevent setting it in a memberwise initializer, which can conflict with the storage management that SwiftUI provides:

```swift
struct PlayButton: View {
    @State private var isPlaying: Bool = false // Create the state.

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") { // Read the state.
            isPlaying.toggle() // Write the state.
        }
    }
}
```

[State Documentation](https://developer.apple.com/documentation/swiftui/state)

##### Binding

A property wrapper type that can read and write a value owned by a source of truth.

Use a binding to create a two-way connection between a property that stores data, and a view that displays and changes the data. A binding connects a property to a source of truth stored elsewhere, instead of storing data directly. For example, a button that toggles between play and pause can create a binding to a property of its parent view using the `Binding` property wrapper.

The parent view declares a property to hold the playing state, using the `State` property wrapper to indicate that this property is the value’s source of truth:

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool


    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}

struct PlayerView: View {
    @State var isPlaying: Bool = false


    var body: some View {
        VStack {
            Text("New episode")
                .foregroundStyle(isPlaying ? .primary : .secondary)
            PlayButton(isPlaying: $isPlaying)
        }
    }
}
```

[Binding Documentation](https://developer.apple.com/documentation/swiftui/binding)

##### StateObject

A property wrapper type that instantiates an observable object.

Use a state object as the single source of truth for a reference type that you store in a view hierarchy. Create a state object in a `View` by applying the `@StateObject` attribute to a property declaration and providing an initial value that conforms to the `ObservableObject` protocol. Declare state objects as private to prevent setting them from a memberwise initializer, which can conflict with the storage management that SwiftUI provides.

In this example, the `DataModel` class conforms to the `ObservableObject` protocol and has two published properties: `name`, a string initialized to "Some Name," and `isEnabled`, a boolean initialized to `false`. These properties can be observed for changes in SwiftUI views.

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MySubView: View {
    var body: some View {
        Text("Subview")
    }
}

struct MyView: View {
    @StateObject private var model = DataModel() // Create the state object.

    var body: some View {
        Text(model.name) // Updates when the data model changes.
        MySubView()
            .environmentObject(model)
    }
}
```

[StateObject Documentation](https://developer.apple.com/documentation/swiftui/stateobject)

##### ObservedObject

A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.

Add the `@ObservedObject` attribute to a parameter of a SwiftUI `View` when the input is an `ObservableObject` and you want the view to update when the object’s published properties change. You typically do this to pass a `StateObject` into a subview.

The following example defines a data model as an observable object, instantiates the model in a view as a state object, and then passes the instance to a subview as an observed object:

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Text(model.name)
        MySubView(model: model)
    }
}

struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Toggle(model.isEnabled ? "Enabled" : "Disabled", isOn: $model.isEnabled)
    }
}
```

[ObservedObject Documentation](https://developer.apple.com/documentation/swiftui/observedobject)

##### EnvironmentObject

A property wrapper type for an observable object that a parent or ancestor view supplies.

An environment object invalidates the current view whenever the observable object that conforms to `ObservableObject` changes. If you declare a property as an environment object, be sure to set a corresponding model object on an ancestor view by calling its `environmentObject(_:)` modifier.

Here's an example:

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Text(model.name)
        MySubView()
            .environmentObject(model)
    }
}

struct MySubView: View {
    @EnvironmentObject var model: DataModel

    var body: some View {
        Toggle(model.isEnabled ? "Enabled" : "Disabled", isOn: $model.isEnabled)
    }
}
```

[EnvironmentObject Documentation](https://developer.apple.com/documentation/swiftui/environmentobject)

### Level Intermediate

#### Module 13: Components in SwiftUI

##### Button Part I

You create a button by providing an action and a label. The action is either a method or closure property that does something when a user clicks or taps the button. The label is a view that describes the button’s action — for example, by showing text, an icon, or both.

The label of a button can be any kind of view, such as a `Text` view for text-only labels or a `Label` view, for buttons with both a title and an icon:

```swift
struct ButtonView: View {
    var body: some View {
        Button(action: signIn) {
            Text("Sign In") // Only Title

            // Label("Sign In", systemImage: "arrow.up")
            // Title and an icon
        }
    }

    func signIn() {
        // do something
    }
}
```

[Button Documentation](https://developer.apple.com/documentation/swiftui/button)

##### Button Part II

You can optionally initialize

 a button with a `ButtonRole` that characterizes the button’s purpose. For example, you can create a `destructive` button for a deletion action:

```swift
struct ButtonView: View {
    var body: some View {
        Button("Delete", role: .destructive, action: delete)
    }

    func delete() {
        // do something
    }
}
```

[Button Documentation](https://developer.apple.com/documentation/swiftui/button#Assigning-a-role)

##### Button Part III

You can customize a button’s appearance using one of the standard button styles, like `bordered`, and apply the style with the `buttonStyle(_:)` modifier:

```swift
struct ButtonView: View {
    var body: some View {
        Button("Sign In", action: signIn)
            .buttonStyle(.bordered)
    }

    func signIn() {
        // do something
    }
}
```

[Button Documentation](https://developer.apple.com/documentation/swiftui/button#Styling-buttons)

##### TextField

You create a text field with a label and a binding to a value. If the value is a string, the text field updates this value continuously as the user types or otherwise edits the text in the field. For non-string types, it updates the value when the user commits their edits, such as by pressing the Return key.

The following example shows a text field to accept a username, and a `Text` view below it that shadows the continuously updated value of username. The `Text` view changes color as the user begins and ends editing. When the user submits their completed entry to the text field, the `onSubmit(of:_:)` modifer calls an internal `validate(name:)` method.

```swift
struct TextFieldView: View {
    @State private var username: String = ""

    var body: some View {
        TextField(
            "User name (email address)",
            text: $username
        )
        .onSubmit {
            // validate(name: username)
        }
        .textInputAutocapitalization(.never)
        .disableAutocorrection(true)
        .border(.secondary)

        Text(username)
            .foregroundColor(.blue)
    }
}
```

[TextField Documentation](https://developer.apple.com/documentation/swiftui/textfield)

##### Slider

A control for selecting a value from a bounded linear range of values.

A slider consists of a “thumb” image that the user moves between two extremes of a linear “track”. The ends of the track represent the minimum and maximum possible values. As the user moves the thumb, the slider updates its bound value.

The following example shows a slider bound to the value speed. As the slider updates this value, a bound `Text` view shows the value updating. The `onEditingChanged` closure passed to the slider receives callbacks when the user drags the slider. The example uses this to change the color of the value text.

```swift
struct SliderView: View {
    @State private var speed = 50.0
    @State private var isEditing = false

    var body: some View {
        VStack {
            Slider(
                value: $speed,
                in: 0...100,
                onEditingChanged: { editing in
                    isEditing = editing
                }
            )
            Text("\(speed)")
                .foregroundColor(isEditing ? .red : .blue)
        }
    }
}
```

[Slider Documentation](https://developer.apple.com/documentation/swiftui/slider)

##### Toggle

A control for selecting a value from a bounded linear range of values.

You create a toggle by providing an `isOn` binding and a label. Bind `isOn` to a Boolean property that determines whether the toggle is on or off. Set the label to a view that visually describes the purpose of switching between toggle states. For example:

```swift
struct SliderView: View {
    @State private var vibrateOnRing = false

    var body: some View {
        Toggle(isOn: $vibrateOnRing) {
            Text("Vibrate on Ring")
        }
    }
}
```

[Toggle Documentation](https://developer.apple.com/documentation/swiftui/toggle)

##### System Images

Symbol images give you a consistent set of icons to use in your app, and ensure that those icons adapt to different sizes and to app-specific content. A symbol image contains a vector-based shape that scales without losing its sharpness. You generate its final appearance by applying a tint color, or if you’re using SF Symbols 2 or later, you can apply multiple colors to add depth and emphasis to your symbol. You use symbol images in places where you display a simple shape or glyph, such as a bar button item.

In SwiftUI, you use `Image(systemName:)` to load a system symbol image and `Image(_:)` to load your custom symbol, as the following code shows:

```swift
struct SystemImagesView: View {
    var body: some View {
        // Create a system symbol image.
        Image(systemName: "multiply.circle.fill")
    }
}
```

[System Images Documentation](https://developer.apple.com/documentation/uikit/uiimage/configuring_and_displaying_symbol_images_in_your_ui)

#### Module 14: Navigation and Views

##### Navigation

A view that displays a root view and enables you to present additional views over the root view.

Use a navigation stack to present a stack of views over a root view. People can add views to the top of the stack by clicking or tapping a `NavigationLink`, and remove views using built-in, platform-appropriate controls, like a Back button or a swipe gesture. The stack always displays the most recently added view that hasn’t been removed, and doesn’t allow the root view to be removed.

To create navigation links, associate a view with a data type by adding a `navigationDestination(for:destination:)` modifier inside the stack’s view hierarchy. Then initialize a NavigationLink that presents an instance of the same kind of data.

This example defines a view with a list of names displayed using a `NavigationStack`. Each name in the list is a navigation link that, when tapped, navigates to a new view displaying the selected name as text.

```swift
struct NavigationExampleView: View {
    var names: [String] = ["Paul", "Abraham", "Leon", "Elias", "Eren", "Canel"]

    var body: some View {
        NavigationStack {
            List(names, id: \.self) { name in
                NavigationLink(name, value: name)
            }
            .navigationDestination(for: String.self) { name in
                Text(name)
            }
        }
    }
}
```

[NavigationStack Documentation](https://developer.apple.com/documentation/swiftui/navigationstack)

##### TabView

To create a user interface with tabs, place views in a TabView and apply the `tabItem(_:)` modifier to the contents of each tab. On iOS, you can also use one of the badge modifiers, like `badge(_:)`, to assign a badge to each of the tabs.

This example defines a view with `TabView` containing two tabs. The first tab displays "First Tab" with a badge of "2" and an icon of a circle with the number 1. The second tab displays "Second Tab" with a badge of "!" and an icon of a circle with the number 2:

```swift
struct TabViewExample: View {
    var body: some View {
        TabView {
            Text("First Tab")
                .badge("2")
                .tabItem {
                    Image(systemName: "1.circle")
                    Text("First")
                }
            Text("Second Tab")
                .badge("!")
                .tabItem {
                    Image(systemName: "2.circle")
                    Text("Second")
                }
        }
    }
}
```

[TabView Documentation](https://developer.apple.com/documentation/swiftui/tabview)

### Level Advanced

#### Module 15: Advanced SwiftUI-Lectures

##### Rotation Effects

Rotates a view’s rendered output in two dimensions around the specified point.

This example defines a view that includes a state variable `isRotated` initialized to `false` to control the rotation of an arrow image. The view contains an `Image` that rotates 90 degrees when `isRotated` is `true`, with an ease-in-out animation of 1 second. Tapping the image toggles the rotation state:

```swift
struct BasicAnimationView: View {
    @State private var isRotated = false

    var body: some View {
        Image(systemName: "arrow.right.circle.fill")
            .rotationEffect(.degrees(isRotated ? 90 : 0))
            .animation(.easeInOut, value: 1)
            .onTapGesture {
                isRotated.toggle()
            }
    }
}
```

[RotationEffect Documentation](https://developer.apple.com/documentation/swiftui/view/rotationeffect(_:anchor:))

##### Scale Effects

Scales this view’s rendered output by the given vertical and horizontal size amounts, relative to an anchor point.

This example defines a view that includes a state variable `scale` initialized to 1.0 to control the scaling of a star image. The view contains a vertically stacked `Image` with a scaling effect and animation, and a button that increases the scale by 0.5 when tapped, triggering the animation.

```swift
struct AnimationView: View {
    @State private var scale: CGFloat = 1.0

    var body: some View {
        VStack {
            Image(systemName: "star.fill")
                .scaleEffect(scale)
                .animation(.easeInOut, value: 1)
            Button("Animate") {
                scale += 0.5
            }
        }
    }
}
```

[ScaleEffect Documentation](https://developer.apple.com/documentation/swiftui/view/scaleeffect(_:anchor:)-7q7as)

