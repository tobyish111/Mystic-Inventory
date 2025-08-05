# Mystic Inventory

**Mystic Inventory** is a lightweight iOS app that lets you use your iPhone camera to **scan Magic: The Gathering cards** and **add them to a personal collection**, stored locally using SwiftData. It's designed to be faster and more responsive than existing apps by using **OCR (text recognition)** and the **Scryfall API** for accurate card identification — without relying on image matching.

---

## ✨ Features

- 📷 **Scan MTG cards** using your camera (OCR-based)
- 🔍 **Identify cards instantly** using set code and collector number
- 📦 **Add to your collection** with one tap
- 📱 **Device-based storage** with SwiftData (no account required)
- 🧾 **View and manage your cards** in a clean, searchable list or grid

---

## 🔧 Tech Stack

- **iOS 17+**, built with **Swift 6** and **Xcode 16**
- **SwiftUI** for modern, declarative UI
- **SwiftData** for local persistence
- **VisionKit / Vision** for real-time OCR
- **Scryfall API** for accurate card data

---

## 📸 How It Works

1. Launch the scanner and point your camera at a Magic card.
2. The app extracts:
   - **Set code** (e.g., `bro`, `one`)
   - **Collector number** (e.g., `142`)
3. It then calls: https://api.scryfall.com/cards/{set}/{collector_number}

4. The card is matched and displayed — then added to your local collection.

---

## 🗃 Data Model (SwiftData)

```swift
@Model
class MTGCard: Identifiable {
 var id: UUID
 var name: String
 var set: String
 var collectorNumber: String
 var rarity: String
 var imageUrl: String
}****
