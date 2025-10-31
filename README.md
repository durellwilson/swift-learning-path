# Swift Learning Path - Detroit DevRel

Complete learning path using production-ready Swift packages. Learn by building real applications.

## 🎯 Learning Philosophy

**Learn by Building** - Every package includes:
- ✅ Production-ready code
- ✅ Comprehensive tests
- ✅ Real-world examples
- ✅ Best practices
- ✅ Documentation

## 📚 Learning Tracks

### 🌱 Beginner Track (2-4 weeks)

#### Week 1-2: SwiftUI Fundamentals
**Resources**:
- [SwiftUI Essentials](https://github.com/durellwilson/swiftui-essentials)
- [SwiftUI Animations](https://github.com/durellwilson/swiftui-animations)
- [SwiftUI DataFlow](https://github.com/durellwilson/swiftui-dataflow)

**Build**: Todo app with animations
```swift
import SwiftUI
import SwiftUIEssentials

struct TodoApp: View {
    @State private var tasks: [Task] = []
    
    var body: some View {
        List(tasks) { task in
            TaskRow(task: task)
                .swipeActions {
                    Button("Delete", role: .destructive) {
                        delete(task)
                    }
                }
        }
    }
}
```

#### Week 3-4: Data Persistence
**Resources**:
- [Apple Full-Stack Template](https://github.com/durellwilson/apple-fullstack-template)
- [SwiftData Pro Scaffold](https://github.com/durellwilson/swiftdata-pro-scaffold)

**Build**: Notes app with SwiftData
```swift
import SwiftData

@Model
final class Note {
    var title: String
    var content: String
    var createdAt: Date
    
    init(title: String, content: String) {
        self.title = title
        self.content = content
        self.createdAt = Date()
    }
}
```

### 🚀 Intermediate Track (4-8 weeks)

#### Week 5-6: Testing & Quality
**Resources**:
- [Swift TDD Framework](https://github.com/durellwilson/swift-tdd-framework)

**Build**: Tested calculator app
```swift
import XCTest
import SwiftTDDFramework

class CalculatorTests: XCTestCase {
    func testAddition() async throws {
        try await asyncTest {
            let calc = Calculator()
            let result = await calc.add(2, 3)
            XCTAssertEqual(result, 5)
        }
    }
}
```

#### Week 7-8: Machine Learning
**Resources**:
- [CoreML + CreateML Kit](https://github.com/durellwilson/coreml-createml-kit)
- [ML Text Kit](https://github.com/durellwilson/ml-text-kit)

**Build**: Image classifier app
```swift
import CoreMLCreateMLKit

let classifier = try ImageClassifier(modelName: "MyModel")
let results = try await classifier.classify(image)

for result in results {
    print("\(result.label): \(Int(result.confidence * 100))%")
}
```

### 🔬 Advanced Track (8-12 weeks)

#### Week 9-10: Security
**Resources**:
- [Swift Security Toolkit](https://github.com/durellwilson/swift-security-toolkit)
- [Security Awareness Course](https://github.com/durellwilson/security-awareness-course)

**Build**: Secure banking app
```swift
import SwiftSecurityToolkit

let storage = SecureStorage()
let auth = BiometricAuth()

// Authenticate
let authenticated = try await auth.authenticate(reason: "Access account")

if authenticated {
    // Store sensitive data
    try await storage.store(apiKey, key: "api_key")
}
```

#### Week 11-12: Full Ecosystem
**Resources**:
- [Apple Ecosystem Starter](https://github.com/durellwilson/apple-ecosystem-starter)
- [App Intents Pro](https://github.com/durellwilson/appintents-pro)

**Build**: Multi-platform productivity app
```swift
import WidgetKit
import AppIntents

// Widget
struct ProductivityWidget: Widget {
    var body: some WidgetConfiguration {
        StaticConfiguration(kind: "productivity", provider: Provider()) { entry in
            WidgetView(entry: entry)
        }
    }
}

// Siri Intent
struct AddTaskIntent: AppIntent {
    static var title: LocalizedStringResource = "Add Task"
    
    @Parameter(title: "Task Name")
    var name: String
    
    func perform() async throws -> some IntentResult {
        // Add task
        return .result()
    }
}
```

## 🎓 Project-Based Learning

### Project 1: Task Manager (Beginner)
**Duration**: 1 week
**Skills**: SwiftUI, SwiftData, Navigation

**Features**:
- Create/edit/delete tasks
- Mark complete
- Filter by status
- Persist with SwiftData

**Packages Used**:
- SwiftUI Essentials
- Apple Full-Stack Template

### Project 2: Expense Tracker (Intermediate)
**Duration**: 2 weeks
**Skills**: Charts, CloudKit, Testing

**Features**:
- Add expenses
- Categorize spending
- Visualize with charts
- Sync with CloudKit
- Unit tests

**Packages Used**:
- SwiftData Pro Scaffold
- Swift TDD Framework

### Project 3: AI Photo Organizer (Advanced)
**Duration**: 3 weeks
**Skills**: CoreML, Vision, WidgetKit

**Features**:
- Image classification
- Smart albums
- Search by content
- Home screen widget
- Siri shortcuts

**Packages Used**:
- CoreML + CreateML Kit
- Apple Ecosystem Starter
- App Intents Pro

## 🛠️ Development Workflow

### 1. Setup
```bash
# Clone template
git clone https://github.com/durellwilson/apple-fullstack-template.git MyApp
cd MyApp

# Add dependencies
# Edit Package.swift
```

### 2. Test-Driven Development
```swift
// 1. Write test (RED)
func testFeature() async throws {
    let result = await feature.execute()
    XCTAssertEqual(result, expected)
}

// 2. Implement (GREEN)
func execute() async -> Result {
    // Implementation
}

// 3. Refactor
func execute() async -> Result {
    // Improved implementation
}
```

### 3. Build & Deploy
```bash
# Run tests
swift test

# Build
swift build

# Deploy to TestFlight
xcodebuild archive -scheme MyApp
```

## 📊 Learning Metrics

### Beginner Goals
- ✅ Build 3 SwiftUI apps
- ✅ Understand @State, @Binding
- ✅ Use SwiftData for persistence
- ✅ Navigate between views

### Intermediate Goals
- ✅ Write unit tests (80%+ coverage)
- ✅ Implement ML features
- ✅ Use CloudKit sync
- ✅ Handle errors gracefully

### Advanced Goals
- ✅ Multi-platform apps
- ✅ Widgets and App Intents
- ✅ Security best practices
- ✅ Production deployment

## 🤝 Community Learning

### Detroit Swift Meetups
- Monthly workshops
- Code reviews
- Pair programming
- Project showcases

### Online Resources
- [Detroit Tech Equity](https://github.com/durellwilson/DetroitTechEquity)
- [Security Awareness Course](https://durellwilson.github.io/security-awareness-course/)
- GitHub Discussions

### Mentorship
- 1-on-1 code reviews
- Career guidance
- Project feedback
- Interview prep

## 🎯 Career Paths

### iOS Developer
**Skills**: SwiftUI, UIKit, CoreData, Networking
**Projects**: 3-5 portfolio apps
**Timeline**: 6-12 months

### ML Engineer
**Skills**: CoreML, CreateML, Python, TensorFlow
**Projects**: 2-3 ML apps
**Timeline**: 8-12 months

### Full-Stack Swift
**Skills**: SwiftUI, Vapor, PostgreSQL, Docker
**Projects**: 2-3 full-stack apps
**Timeline**: 12-18 months

## 📚 Additional Resources

### Apple Documentation
- [SwiftUI Tutorials](https://developer.apple.com/tutorials/swiftui)
- [Swift Book](https://docs.swift.org/swift-book/)
- [WWDC Videos](https://developer.apple.com/videos/)

### Books
- "SwiftUI by Tutorials" - Ray Wenderlich
- "iOS 18 Programming Fundamentals" - Matt Neuburg
- "Machine Learning by Tutorials" - Ray Wenderlich

### Practice Platforms
- LeetCode (Swift)
- HackerRank
- Project Euler

## 🚀 Next Steps

1. **Choose your track** (Beginner/Intermediate/Advanced)
2. **Clone starter template**
3. **Build first project**
4. **Join Detroit community**
5. **Share your progress**

## 📝 License

MIT License - All learning resources are open source

---

**Learn by building. Build for Detroit.** 🏭

**Start here**: https://github.com/durellwilson/apple-fullstack-template
