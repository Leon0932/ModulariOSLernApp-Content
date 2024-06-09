# Quizzes for SwiftUI

## Table of contents

1. [Beginner](#level-beginner)
      1. [Module 11: Introduction to SwiftUI](#module-11-introduction-to-swiftui)
         1. [Quiz 1: Create a Greeting View](#quiz-1-create-a-greeting-view)
         2. [Quiz 2: Create a Simple VStack](#quiz-2-create-a-simple-vstack)
         3. [Quiz 3: Create a Complex HStack](#quiz-3-create-a-complex-hstack)
         4. [Quiz 4: Overlay Views in ZStack](#quiz-4-overlay-views-in-zstack)
      2. [Module 12: State Management in SwiftUI](#module-12-state-management-in-swiftui)
         1. [Quiz 1: Switch between On and Off](#quiz-1-switch-between-on-and-off)
         2. [Quiz 2: Bind a Toggle Button](#quiz-2-bind-a-toggle-button)
      3. [Module 13: Components in SwiftUI](#module-13-components-in-swiftui)
         1. [Quiz 1: Create a Submit Button](#quiz-1-create-a-submit-button)
         2. [Quiz 2: Create an Update Button](#quiz-2-create-an-update-button)
         3. [Quiz 3: Create an Email TextField](#quiz-3-create-an-email-textfield)
         4. [Quiz 4: Create a Volume Slider](#quiz-4-create-a-volume-slider)
2. [Intermediate](#level-intermediate)
      1. [Module 14: Navigation and Views](#module-14-navigation-and-views)
          1. [Quiz 1: Create a Food Navigation Stack](#quiz-1-create-a-food-navigation-stack)
          2. [Quiz 2: Create a Category Tab View](#quiz-2-create-a-category-tab-view)
3. [Advanced](#level-advanced)
      1. [Module 15: Advanced SwiftUI-Lectures](#module-15-advanced-swiftui-lectures)
         1. [Quiz 1: Create a Rotating Arrow](#quiz-1-create-a-rotating-arrow)
         2. [Quiz 2: Create a Pulsing Heart](#quiz-2-create-a-pulsing-heart)

### Level Beginner

#### Module 11: Introduction to SwiftUI

##### Quiz 1: Create a Greeting View

**Description**: Create a `GreetingView` struct in SwiftUI that displays the text "Welcome to SwiftUI!" with a font size of 30 and color green.

**Starting Code**:
```swift
struct GreetingView: View {
    var body: some View {
        ...
    }
}
```

**Solution Code**:
```swift
struct GreetingView: View {
    var body: some View {
        Text("Welcome to SwiftUI!")
            .font(.system(size: 30))
            .foregroundColor(.green)
    }
}
```

##### Quiz 2: Create a Simple VStack

**Description**: Create a `SimpleVStackView` struct in SwiftUI that displays a vertical stack of 3 text views, each showing the text "Item X" where X is the item number, with a spacing of 15 and center alignment.

**Starting Code**:
```swift
struct SimpleVStackView: View {
    var body: some View {
        VStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct SimpleVStackView: View {
    var body: some View {
        VStack(
            alignment: .center,
            spacing: 15
        ) {
            ForEach(1...3, id: \.self) { item in
                Text("Item \(item)")
            }
        }
    }
}
```

##### Quiz 3: Create a Complex HStack

**Description**: Create a `ComplexHStackView` struct in SwiftUI that displays a horizontal stack of 4 text views, each showing the text "Element X" where X is the element number, with a spacing of 20 and bottom alignment.

**Starting Code**:
```swift
struct ComplexHStackView: View {
    var body: some View {
        HStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct ComplexHStackView: View {
    var body: some View {
        HStack(
            alignment: .bottom,
            spacing: 20
        ) {
            ForEach(1...4, id: \.self) { element in
                Text("Element \(element)")
            }
        }
    }
}
```

##### Quiz 4: Overlay Views in ZStack

**Description**: Create a `OverlayZStackView` struct in SwiftUI that displays a green rectangle with a width and height of 200 points, and overlays a pink text "Center View" on top of it.

**Starting Code**:
```swift
struct OverlayZStackView: View {
    var body: some View {
        ZStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct OverlayZStackView: View {
    var body: some View {
        ZStack {
            Rectangle()
                .fill(Color.green)
                .frame(width: 200, height: 200)
            Text("Center View")
                .foregroundColor(.pink)
        }
    }
}
```

#### Module 12: State Management in SwiftUI

##### Quiz 1: Switch between On and Off

**Description**: Create a `ToggleSwitch` struct in SwiftUI that switches between "On" and "Off" when clicked, using a state variable.

**Starting Code**:
```swift
struct ToggleSwitch: View {
    @State private var isOn: Bool = false

    var body: some View {
        ...
    }
}
```

**Solution Code**:
```swift
struct ToggleSwitch: View {
    @State private var isOn: Bool = false

    var body: some View {
        Button(isOn ? "Off" : "On") {
            isOn.toggle()
        }
    }
}
```

##### Quiz 2: Bind a Toggle Button

**Description**: 
1) Create a `ToggleButton` struct in SwiftUI that toggles between "Start" and "Stop" using a binding variable.
2) Then, create a `ControlView` struct that uses `ToggleButton` and binds its `isStarted` state.

**Starting Code**:
```swift
struct ToggleButton: View {
    @Binding private var isStarted: Bool

    var body: some View {
        ...
    }
}

struct ControlView: View {
    @State private var isStarted: Bool = false

    var body: some View {
        ...
    }
}
```

**Solution Code**:
```swift
struct ToggleButton: View {
    @Binding private var isStarted: Bool

    var body: some View {
        Button(isStarted ? "Stop" : "Start") {
            isStarted.toggle()
        }
    }
}

struct ControlView: View {
    @State private var isStarted: Bool = false

    var body: some View {
        VStack {
            ToggleButton(isStarted: $isStarted)
        }
    }
}
```

#### Module 13: Components in SwiftUI

##### Quiz 1: Create a Submit Button

**Description**: 
1) Create a `SubmitButtonView` struct in SwiftUI that displays a button with the title "Submit".
2) The button should call a function `submit` when tapped.

**Starting Code**:
```swift
struct SubmitButtonView: View {
    var body: some View {
        Button(action: submit) {
            ...
        }
    }

    func submit() {
        // perform submit action
    }
}
```

**Solution Code**:
```swift
struct SubmitButtonView: View {
    var body: some View {
        Button(action: submit) {
            Text("Submit")
        }
    }

    func submit() {
        // perform submit action
    }
}
```

##### Quiz 2: Create an Update Button

**Description**: 
1) Create a `UpdateButtonView` struct in SwiftUI that displays a button with the title "Update" and a prominent role.
2) The button should call a function `update` when tapped.

**Starting Code**:
```swift
struct UpdateButtonView: View {
    var body: some View {
        Button("Update", role: .prominent, action: update)
    }

    func update() {
        // perform update action
    }
}
```

**Solution Code**:
```swift
struct UpdateButtonView: View {
    var body: some View {
        Button("Update", role: .prominent, action: update)
    }

    func update() {
        // perform update action
    }
}
```

##### Quiz 3: Create an Email TextField

**Description**: 
1) Create a `EmailTextFieldView` struct in SwiftUI that displays a text field with the placeholder "Email address" for entering an email.
2) The text field should have a border of a secondary color, disable autocorrection, and use no text input autocapitalization.
3) Below the text field, display the entered email in red text.

**Starting Code**:
```swift
struct EmailTextFieldView: View {
    @State private var email: String = ""

    var body: some View {
        VStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct EmailTextFieldView: View {
    @State private var email: String =

 ""

    var body: some View {
        VStack {
            TextField("Email address", text: $email)
                .textInputAutocapitalization(.never)
                .disableAutocorrection(true)
                .border(.secondary)
            Text(email)
                .foregroundColor(.red)
        }
    }
}
```

##### Quiz 4: Create a Volume Slider

**Description**: 
1) Create a `VolumeSliderView` struct in SwiftUI that displays a slider for selecting a volume value between 0 and 100.
2) Below the slider, display the selected volume value in green text while editing and gray text otherwise.

**Starting Code**:
```swift
struct VolumeSliderView: View {
    @State private var volume = 50.0
    @State private var isEditing = false

    var body: some View {
        VStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct VolumeSliderView: View {
    @State private var volume = 50.0
    @State private var isEditing = false

    var body: some View {
        VStack {
            Slider(
                value: $volume,
                in: 0...100,
                onEditingChanged: { editing in
                    isEditing = editing
                }
            )
            Text("\(volume)")
                .foregroundColor(isEditing ? .green : .gray)
        }
    }
}
```
### Level Intermediate

#### Module 14: Navigation and Views

##### Quiz 1: Create a Food Navigation Stack

**Description**: 
1) Create a `FoodNavigationView` struct in SwiftUI that displays a list of food items using a `NavigationStack`.
2) Each food item should be a navigation link that navigates to a new view displaying the selected food name.

**Starting Code**:
```swift
struct FoodNavigationView: View {
    var foodItems: [String] = ["Apple", "Banana", "Carrot", "Date", "Eggplant"]

    var body: some View {
        NavigationStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct FoodNavigationView: View {
    var foodItems: [String] = ["Apple", "Banana", "Carrot", "Date", "Eggplant"]

    var body: some View {
        NavigationStack {
            List(foodItems, id: \.self) { food in
                NavigationLink(food, value: food)
            }
            .navigationDestination(for: String.self) { food in
                Text(food)
            }
        }
    }
}
```

##### Quiz 2: Create a Category Tab View

**Description**: 
1) Create a `CategoryTabView` struct in SwiftUI that displays a `TabView` with two tabs.
2) The first tab should display "Fruits" with a badge of "5" and an icon of an apple. 
3) The second tab should display "Vegetables" with a badge of "3" and an icon of a carrot.

**Starting Code**:
```swift
struct CategoryTabView: View {
    var body: some View {
        TabView {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct CategoryTabView: View {
    var body: some View {
        TabView {
            Text("Fruits")
                .badge("5")
                .tabItem {
                    Image(systemName: "applelogo")
                    Text("Fruits")
                }
            Text("Vegetables")
                .badge("3")
                .tabItem {
                    Image(systemName: "leaf")
                    Text("Vegetables")
                }
        }
    }
}
```

### Level Advanced

#### Module 15: Advanced SwiftUI-Lectures

##### Quiz 1: Create a Rotating Arrow

**Description**: Create a `RotatingArrowView` struct in SwiftUI that displays an arrow image which rotates 180 degrees when tapped, with an ease-out animation of 2 seconds.

**Starting Code**:
```swift
struct RotatingArrowView: View {
    @State private var isRotated = false

    var body: some View {
        ...
    }
}
```

**Solution Code**:
```swift
struct RotatingArrowView: View {
    @State private var isRotated = false

    var body: some View {
        Image(systemName: "arrow.right.circle.fill")
            .rotationEffect(.degrees(isRotated ? 180 : 0))
            .animation(.easeOut(duration: 2), value: isRotated)
            .onTapGesture {
                isRotated.toggle()
            }
    }
}
```

##### Quiz 2: Create a Pulsing Heart

**Description**: Create a `PulsingHeartView` struct in SwiftUI that displays a heart image which scales up by 0.2 when a button is tapped, with an ease-in animation of 0.5 seconds.

**Starting Code**:
```swift
struct PulsingHeartView: View {
    @State private var scale: CGFloat = 1.0

    var body: some View {
        VStack {
            ...
        }
    }
}
```

**Solution Code**:
```swift
struct PulsingHeartView: View {
    @State private var scale: CGFloat = 1.0

    var body: some View {
        VStack {
            Image(systemName: "heart.fill")
                .scaleEffect(scale)
                .animation(.easeIn(duration: 0.5), value: scale)
            Button("Pulse") {
                scale += 0.2
            }
        }
    }
}
```
