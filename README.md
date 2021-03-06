# GymVisual

[GymVisual](https://gymvisual.com) contains videos, pictures, gifs, and information on over 2600+ different exercises. This package contains Swift models mapped from their [Exercise List CSV](https://gymvisual.com/blog/how-to/list-of-exercises), in an easy to use format. 
All types conform to `CaseIterable`, `Codable`, `Identifiable`, `Equatable`, & `Hashable`.


> ⚠️ GymVisual's illustrations, videos, and gifs are paid resources. You will need to purchase them yourself and host them independently.

## Types

```swift
public struct Exercise {
  let id: Int
  let name: String
  let media: String
  let sex: Sex
  let type: ExerciseType
  let equipment: Equipment
  let bodyparts: [BodyPart]
  let primaryMuscles: [Muscle]
  let secondaryMuscles: [Muscle]
}

extension Exercise: Codable {}
extension Exercise: Equatable {}
extension Exercise: Hashable {}
extension Exercise: Identifiable {}
extension Equipment: CaseIterable { ... }
```

```swift
enum BodyPart: String {
  case waist         = "Waist"
  case chest         = "Chest"
  case back          = "Back"
  case upperArms     = "Upper Arms"
  case hips          = "Hips"
  case shoulders     = "Shoulders"
  case thighs        = "Thighs"
  case forearms      = "Forearms"
  case calves        = "Calves"
  case neck          = "Neck"
  case cardio        = "Cardio"
  case plyometrics   = "Plyometrics"
  case yoga          = "Yoga"
  case fullBody      = "Full body"
  case weightlifting = "Weightlifting"
  case stretching    = "Stretching"
  case pilates       = "Pilates"
}

extension BodyPart: Codable {}
extension BodyPart: Equatable {}
extension BodyPart: Hashable {}
extension BodyPart: CaseIterable {}
extension BodyPart: Identifiable { public var id: String { rawValue } }
extension BodyPart: CustomStringConvertible { public var description: String { rawValue } }
```

```swift
enum Equipment: String {
  case bodyWeight      = "Body weight"
  case leverageMachine = "Leverage machine"
  case stabilityBall   = "Stability ball"
  case barbell         = "Barbell"
  case rope            = "Rope"
  case cable           = "Cable"
  case dumbbell        = "Dumbbell"
  case ezBarbell       = "EZ Barbell"
  case kettlebell      = "Kettlebell"
  case medicineBall    = "Medicine Ball"
  case olympicBarbell  = "Olympic barbell"
  case weighted        = "Weighted"
  case bosuBall        = "Bosu ball"
  case sledMachine     = "Sled machine"
  case smithMachine    = "Smith machine"
  case wheelRoller     = "Wheel roller"
  case trapBar         = "Trap bar"
  case band            = "Band"
  case suspension      = "Suspension"
  case assisted        = "Assisted"
  case resistanceBand  = "Resistance Band"
  case roll            = "Roll"
  case powerSled       = "Power Sled"
  case vibratePlate    = "Vibrate Plate"
  case battlingRope    = "Battling Rope"
  case rollball        = "Rollball"
  case stick           = "Stick"
}

extension Equipment: Codable {}
extension Equipment: Equatable {}
extension Equipment: Hashable {}
extension Equipment: CaseIterable {}
extension Equipment: Identifiable { public var id: String { rawValue } }
extension Equipment: CustomStringConvertible { public var description: String { rawValue } }
```

```swift
enum ExerciseType: String {
  case strength   = "Strength"
  case aerobic    = "Aerobic"
  case stretching = "Stretching"
}

extension ExerciseType: Codable {}
extension ExerciseType: Equatable {}
extension ExerciseType: Hashable {}
extension ExerciseType: CaseIterable {}
extension ExerciseType: Identifiable { public var id: String { rawValue } }
extension ExerciseType: CustomStringConvertible { public var description: String { rawValue } }
```

```swift
enum Muscle: String {
  case wristFlexors                  = "Wrist Flexors"
  case wristExtensors                = "Wrist Extensors"
  case tricepsBrachii                = "Triceps Brachii"
  case trapeziusUpperFibers          = "Trapezius Upper Fibers"
  case trapeziusMiddleFibers         = "Trapezius Middle Fibers"
  case trapeziusLowerFibers          = "Trapezius Lower Fibers"
  case trapezius                     = "Trapezius"
  case transverseAbdominus           = "Transverse Abdominus"
  case tibialisAnterior              = "Tibialis Anterior"
  case teresMinor                    = "Teres Minor"
  case teresMajor                    = "Teres Major"
  case tensorFasciaeLatae            = "Tensor Fasciae Latae"
  case subscapularis                 = "Subscapularis"
  case sternocleidomastoid           = "Sternocleidomastoid"
  case splenius                      = "Splenius"
  case soleus                        = "Soleus"
  case serratusAnterior              = "Serratus Anterior"
  case sartorius                     = "Sartorius"
  case rhomboids                     = "Rhomboids"
  case rectusAbdominis               = "Rectus Abdominis"
  case quadriceps                    = "Quadriceps"
  case pectoralisMajorSternalHead    = "Pectoralis Major Sternal Head"
  case pectoralisMajorClavicularHead = "Pectoralis Major Clavicular Head"
  case pectineous                    = "Pectineous"
  case obliques                      = "Obliques"
  case levatorScapulae               = "Levator Scapulae"
  case latissimusDorsi               = "Latissimus Dorsi"
  case infraspinatus                 = "Infraspinatus"
  case iliopsoas                     = "Iliopsoas"
  case hamstrings                    = "Hamstrings"
  case gracilis                      = "Gracilis"
  case gluteusMinimus                = "Gluteus Minimus"
  case gluteusMedius                 = "Gluteus Medius"
  case gluteusMaximus                = "Gluteus Maximus"
  case gastrocnemius                 = "Gastrocnemius"
  case erectorSpinae                 = "Erector Spinae"
  case deltoidPosterior              = "Deltoid Posterior"
  case deltoidLateral                = "Deltoid Lateral"
  case deltoidAnterior               = "Deltoid Anterior"
  case brachioradialis               = "Brachioradialis"
  case brachialis                    = "Brachialis"
  case bicepsBrachii                 = "Biceps Brachii"
  case adductorMagnus                = "Adductor Magnus"
  case adductorLongus                = "Adductor Longus"
  case adductorBrevis                = "Adductor Brevis"
}

extension Muscle: Codable {}
extension Muscle: Equatable {}
extension Muscle: Hashable {}
extension Muscle: CaseIterable {}
extension Muscle: Identifiable { public var id: String { rawValue } }
extension Muscle: CustomStringConvertible { public var description: String { rawValue } }
```

```swift
enum Sex: String {
  case male = "Male"
  case female = "Female"
}

extension Sex: Codable {}
extension Sex: Equatable {}
extension Sex: Hashable {}
extension Sex: CaseIterable {}
extension Sex: Identifiable { public var id: String { rawValue } }
extension Sex: CustomStringConvertible { public var description: String { rawValue } }
```
