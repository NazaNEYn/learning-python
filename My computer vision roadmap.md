# Computer Vision Roadmap for Beginners

This document outlines a structured path for individuals with a Python background but no prior experience in Machine Learning or Computer Vision, aiming for practical results within a few months.

---

## 1️⃣ Beginner-Friendly Computer Vision Roadmap (for YOU)

This roadmap assumes:
* ~6 months of Python
* No ML / CV background
* You want practical results early

### 🟢 Stage 0 — Python cleanup (1–2 weeks, parallel)

You do **NOT** need advanced Python. Just make sure you’re comfortable with:

* Lists, tuples, dictionaries
* Functions
* Loops & conditions
* Basic NumPy arrays

> **Tip:** If NumPy feels new: learn it only as needed (don’t deep dive).

---

### 🟢 Stage 1 — “Seeing images as data” (2–3 weeks)

This is where CV becomes fun.

**Concepts (no math heavy stuff):**
* What an image is (pixels = numbers) 
* RGB vs Grayscale
* Image size & channels
* Reading and showing images
* Drawing shapes & text on images

**Tool:** OpenCV (cv2)

**Mini-projects:**
* Load and display images
* Convert color spaces
* Draw bounding boxes
* Simple image editor (blur, resize, crop)

**🎯 Goal:** “I understand how computers see images”

---

### 🟢 Stage 2 — Image processing basics (3–4 weeks)

This is classic CV (no ML yet).

**Learn:**
* Blurring & smoothing
* Edge detection (Canny) 
* Thresholding
* Contours
* Morphological operations

**Mini-projects:**
* Edge detector
* Shape detector
* Document scanner (like CamScanner)
* Motion detection with webcam

**🎯 Goal:** “I can extract useful information from images”

---

### 🟢 Stage 3 — Video & real-time CV (2–3 weeks)

This is where things feel powerful.

**Learn:**
* Webcam access
* Frame-by-frame processing
* FPS concepts
* Simple object tracking

**Mini-projects:**
* Motion-based intruder detection
* Color-based object tracker
* Face detection (Haar cascades — old but great for learning)

**🎯 Goal:** “I can build real-time CV applications”

---

### 🟡 Stage 4 — Machine Learning for CV (light intro) (3–4 weeks)

Now we gently step into ML.

**Learn:**
* What ML is (intuition, not theory)
* Classification vs detection 
* Train/test split
* Overfitting (conceptually)

**Tool:**
* scikit-learn (very basic)
* Then move to pretrained deep learning models

**Mini-projects:**
* Image classifier (cats vs dogs)
* Digit recognition (MNIST)
* Simple face recognition

**🎯 Goal:** “I understand how models learn from images”

---

### 🟠 Stage 5 — Deep Learning for CV (optional, later)

Only start this when:
* Stages 1–4 feel comfortable
* You still enjoy CV

**Learn:**
* CNN intuition
* Transfer learning
* YOLO / SSD (using them, not building them)

---

## 2️⃣ Course vs Roadmap — honest answer

**❓ Do you need a course?**
No — but beginners often benefit from **ONE** good course.

**❗ The danger**
* Taking multiple courses
* Watching without building
* Feeling “I finished the course, now what?”

**✅ Best approach (I strongly recommend this)**
Use a roadmap + ONE course as a guide

Think of a course as:
> “Someone holding your hand while you walk the roadmap”

Not as:
> “This course will make me a CV engineer”

**🧠 My recommendation for you**
* Use **ONE** structured beginner CV course
* Ignore advanced sections
* Build your own mini-projects alongside it

If you want, I can suggest:
* A very beginner-friendly CV course
* Or a free YouTube-based path
* Or a project-first approach (learn only when stuck)

---

## 3️⃣ How to avoid overwhelm (this is key)

**🧘 Rule #1: One topic at a time**
Not:
> “CV + ML + AI + YOLO + math”

Instead:
> “Today I learn how to read and show images”

**🧘 Rule #2: Code > Videos**
For every:
* 30 minutes watching
* Do 60 minutes coding

Even if it’s messy.

**🧘 Rule #3: Confusion is normal**
When you think:
> “I don’t understand half of this”

That actually means:
> “I’m learning the right thing”

**🧘 Rule #4: Don’t compare yourself**
Most “CV developers” online:
* Had years of background
* Or are showing highlights, not struggle

<hr><hr>


# Computer Vision Roadmap: A Beginner's Guide (Python)

## Short answer (so you can breathe)
* ✅ You do **NOT** need a big course to start.
* ✅ A clear roadmap + small projects is the best way not to get overwhelmed.
* ✅ You can add a course later, when things start to make sense.

> Think of a course as a map legend, not the whole journey.

---

## Beginner-Friendly Computer Vision Roadmap (Python)

This roadmap assumes:
* You already know basic Python (loops, functions, lists, etc.)
* You’re curious but new to CV
* We’ll move from **visual + fun** → **slightly technical** → **powerful**

---

### PHASE 0 (1–2 days): Prepare your mindset ⚠️
Before touching CV:
* You are not supposed to understand everything
* Confusion ≠ failure
* CV learning is non-linear

**Rule:**
> If you understand 60%, you’re doing great.

---

### PHASE 1 (1–2 weeks): What images really are 🧠🖼️

**Goal**
Understand images as data, not magic.

**Learn:**
* What is a pixel?
* Image = matrix (array of numbers) 
* RGB vs Grayscale
* Image size, channels

**Tools:**
* `numpy`
* `opencv-python`

**Mini projects:**
* Load and display an image
* Convert image to grayscale
* Resize and crop images
* Draw shapes on images

👉 This phase is very visual and rewarding.

---

### PHASE 2 (1–2 weeks): Image processing basics 🔧

**Goal**
Learn how computers “see” edges and shapes.

**Learn:**
* Blurring & smoothing
* Edge detection (Canny) 
* Thresholding
* Contours
* Color detection (HSV)

**Mini projects:**
* Edge detector
* Shape detection (circle / rectangle)
* Color-based object detection (track a red object)
* Motion detection using webcam

> This is where CV starts feeling alive.

---

### PHASE 3 (2–3 weeks): Video & real-time CV 🎥

**Goal**
Work with webcam/video streams.

**Learn:**
* Reading video frames
* FPS and real-time constraints
* Simple object tracking

**Mini projects:**
* Webcam face detection (Haar cascades)
* Motion tracking
* Simple “security camera”

> ⚠️ No deep learning yet — this builds confidence.

---

### PHASE 4 (3–4 weeks): Intro to ML for CV 🤖

**Goal**
Understand why models are needed.

**Learn:**
* What a model is
* Training vs prediction
* Classification vs detection 
* Very basic ML concepts

**Tools:**
* `scikit-learn`

**Mini projects:**
* Image classifier (cats vs dogs — tiny dataset)
* Handwritten digit recognition (MNIST)

> Don’t worry if this feels slower — it’s normal.

---

### PHASE 5 (4–6 weeks): Deep Learning for CV 🔥

**Goal**
Use powerful models without drowning in theory.

**Learn:**
* CNN intuition (not math-heavy)
* Transfer learning 
* Pre-trained models

**Tools:**
* PyTorch (recommended) or TensorFlow
* YOLO / MobileNet

**Mini projects:**
* Face mask detector
* Object detection on webcam
* Gesture recognition

> At this point, you’re officially doing CV.

---

## Do you need a course?

**Honest answer:** Not immediately

**When a course helps:**
* ✔ You feel lost after Phase 2
* ✔ You want structured explanations
* ✔ You keep jumping topics

**When a course hurts:**
* ❌ You binge-watch without coding
* ❌ You follow blindly without understanding
* ❌ You feel “behind” because of pacing

**Best strategy (I strongly recommend this)**

**Step 1 (Now)**
* 👉 Follow this roadmap
* 👉 Build small projects
* 👉 Google / YouTube specific problems

**Example:**
> “opencv detect red color python”

**Step 2 (Later)**
Add **ONE** well-rated CV course to:
* Fill gaps
* Connect concepts
* Learn best practices

> Not 3 courses. One.

---

## How to avoid overwhelm (very important)

**Rule of 3**
Only focus on:
* One topic
* One library
* One small project

At a time.

**Daily learning structure (simple)**
🕒 60–90 minutes per day:
* 20 min: read/watch
* 40 min: code
* 10 min: break & reflection

> Stop when tired — not when “finished”.

---

## Final reassurance (please read this)
* You’re not late.
* You’re not behind.
* You’re not “bad at math”.

You’re early in a field that rewards curiosity and patience.

<hr><hr>


# 🧭 8-Week Beginner Computer Vision Plan (3h/day)

This plan provides a structured, step-by-step approach to learning Computer Vision, focusing on consistency and practical application over speed.

---

## Daily structure (important)

Each day follows the same calm structure:

* 🧠 **30 min** → Learn (video/article)
* 👨‍💻 **1h 45 min** → Code & experiment
* ✍️ **15 min** → Notes / reflect / commit code
* ☕ **Breaks** whenever needed

> If something takes longer, stop anyway. **Consistency > speed.**

---

## WEEK 1 — Images are Data (Foundation Week)

**Goal**
Understand what an image really is and get comfortable with OpenCV.

| Day | Topic | Build |
| :--- | :--- | :--- |
| **Day 1** | Install: `opencv-python`, `numpy`, `matplotlib`. Load and display an image. Print image shape and data type. | Program that loads an image and displays: Original, Grayscale version. |
| **Day 2** | Learn RGB vs Grayscale. Access pixel values. Change individual pixels. | Program that: Draws a colored square, Writes text on an image. |
| **Day 3** | Resize, crop, rotate images. Understand image dimensions. | Image editor script: Resize, Crop center, Rotate. |
| **Day 4** | Learn image channels (R, G, B). Split and merge channels. | Display each color channel separately . |
| **Day 5** | 🎯 **Mini Project 1: Simple Image Playground** | Load any image. Apply: Grayscale, Resize, Draw shapes. Switch effects using keyboard keys. |

> **🧠 This week is slow on purpose.**

---

## WEEK 2 — Image Processing Basics

**Goal**
Learn how computers detect edges and shapes.

| Day | Topic | Build |
| :--- | :--- | :--- |
| **Day 1** | Blurring (Gaussian blur). Why smoothing matters. | Compare original vs blurred image. |
| **Day 2** | Edge detection (Canny). | Edge detector app with adjustable thresholds . |
| **Day 3** | Thresholding (binary images). | Convert image to black & white. Try different threshold values. |
| **Day 4** | Contours and shapes. | Detect rectangles and circles in images . |
| **Day 5** | 🎯 **Mini Project 2: Shape Detector** | Input image. Detect and label: Circles, Rectangles, Other shapes. |

---

## WEEK 3 — Color & Motion

**Goal**
Track objects by color and detect motion.

| Day | Topic | Build |
| :--- | :--- | :--- |
| **Day 1** | HSV color space. Why RGB fails sometimes. | Detect a red object in an image . |
| **Day 2** | Webcam basics. Read live frames. | Show webcam feed with FPS counter. |
| **Day 3** | Color tracking using webcam. | Track a colored object in real time. |
| **Day 4** | Background subtraction. Motion detection. | Motion detector with bounding boxes. |
| **Day 5** | 🎯 **Mini Project 3: Color-Based Object Tracker** | Track any colored object via webcam. Draw bounding box + center point. |

> This is where CV starts feeling magical ✨

---

## WEEK 4 — Face Detection & Real-Time CV

**Goal**
Work with classical CV models (no ML yet).

| Day | Topic | Build |
| :--- | :--- | :--- |
| **Day 1** | What Haar cascades are. Face detection basics. | Face detector on images . |
| **Day 2** | Face detection on webcam. | Real-time face detector. |
| **Day 3** | Eye detection. Multiple object detection. | Face + eye detection app. |
| **Day 4** | Performance optimization. Resize frames for speed. | |
| **Day 5** | 🎯 **Mini Project 4: Smart Camera** | Face detection, Motion detection, FPS display, Keyboard controls (on/off). |

> **At this point you’re already doing CV.**

---

## WEEK 5 — Intro to ML (Gentle Entry)

**Goal**
Understand why deep learning exists.

| Day | Topic | Build |
| :--- | :--- | :--- |
| **Day 1** | What is a model? Training vs prediction. | |
| **Day 2** | Image classification idea. Feature vectors (high level). | |
| **Day 3** | MNIST dataset (digits). | Digit classifier (using `sklearn`). |
| **Day 4** | Evaluate accuracy. Understand mistakes. | |
| **Day 5** | 🎯 **Mini Project 5: Handwritten Digit Recognizer** | |

---

## WEEK 6–7 — Deep Learning for CV (Carefully)

**Goal**
Use powerful models without drowning.

| Learn | Build |
| :--- | :--- |
| CNN intuition  | Image classifier using pre-trained model |
| Pre-trained models | Webcam object detection (YOLO) |
| Transfer learning | |

---

## WEEK 8 — Portfolio Project

**🎯 Choose ONE:**
* Face mask detector
* Gesture recognition
* Object detection app
* Smart surveillance camera

---

## 🔑 Important rules (please follow)

* If you feel stuck **> 30 minutes** → Google
* If still stuck → **simplify**
* If exhausted → **stop**
* Code > videos
* One project at a time

---

## Final truth (very important)

* If you complete Weeks 1–4, you are no longer a beginner in CV.
* If you complete Weeks 1–8, you can confidently say: **“I build computer vision systems with Python.”**

<hr><hr>


# Your 8-Week Computer Vision Starter Plan (3 hrs/day)

This plan is designed for beginners to gain confidence and practical skills in Computer Vision (CV) with a focus on consistency over speed.

## Schedule assumption

* ⏱️ ~3 hours/day
* 📅 5 days/week (take weekends off or use them lightly)
* 🎯 Goal: confidence + real CV projects, not mastery

---

## DAILY STRUCTURE (same every day)

| Time Slot | Activity | Focus |
| :--- | :--- | :--- |
| **Hour 1** | Learn | Short video / article, Take minimal notes |
| **Hour 2** | Code | Follow examples, Modify them |
| **Hour 3** | Build | Small task or mini-project, Break things on purpose |

> This structure prevents overwhelm.

---

## WEEK 1: Images Are Data 🖼️

**Goal**
Understand what images actually are and get comfortable with OpenCV.

| Learn | Tools |
| :--- | :--- |
| Pixels & image arrays | Python |
| RGB vs grayscale  | OpenCV (cv2) |
| Loading & displaying images | NumPy |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | Install OpenCV. Load & display an image. Print image shape. |
| **Day 2** | Convert to grayscale. Resize & crop images. |
| **Day 3** | Draw lines, circles, rectangles on images. |
| **Day 4** | Split RGB channels. Change brightness & contrast. |
| **Day 5** | 🎯 **Mini Project: Image Playground** Load any image. Apply 3 transformations. Display before & after. |

> ✅ **Result:** Images stop feeling “mystical”

---

## WEEK 2: Image Processing Basics 🔧

**Goal**
Learn how computers find edges, shapes, and colors.

| Learn |
| :--- |
| Blurring |
| Edge detection  |
| Thresholding |
| Contours |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | Gaussian blur. Why noise matters. |
| **Day 2** | Canny edge detection. |
| **Day 3** | Thresholding (binary images). |
| **Day 4** | Contours & shape detection. |
| **Day 5** | 🎯 **Mini Project: Shape Detector** Detect circles & rectangles in an image. Draw bounding boxes. |

> ✅ **Result:** You’re “seeing” like a computer

---

## WEEK 3: Color & Motion 🎨🎥

**Goal**
Work with color spaces and detect movement.

| Learn |
| :--- |
| HSV color space  |
| Webcam frames |
| Frame differencing |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | RGB vs HSV. Convert images to HSV. |
| **Day 2** | Detect a specific color (red/blue). |
| **Day 3** | Read webcam video. Display real-time frames. |
| **Day 4** | Simple motion detection. |
| **Day 5** | 🎯 **Mini Project: Color Tracking App** Track a colored object using webcam. |

> ✅ **Result:** Real-time CV feels exciting

---

## WEEK 4: Face Detection (Classic CV) 😄

**Goal**
Build something impressive without deep learning yet.

| Learn |
| :--- |
| Haar cascades |
| Face detection basics  |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | What face detection is. Load Haar model. |
| **Day 2** | Detect faces in images. |
| **Day 3** | Detect faces in webcam video. |
| **Day 4** | Improve accuracy & speed. |
| **Day 5** | 🎯 **Mini Project: Face Detection App** Draw boxes around faces. Show face count. |

> ✅ **Result:** Confidence boost 💪

---

## WEEK 5: Intro to Machine Learning 🤖

**Goal**
Understand why deep learning exists.

| Learn | Tools |
| :--- | :--- |
| What a model is | `scikit-learn` |
| Training vs inference | |
| Classification concept  | |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | ML basics (no math heavy). |
| **Day 2** | Train a simple image classifier. |
| **Day 3** | Test & evaluate predictions. |
| **Day 4** | Improve results (resize, normalize). |
| **Day 5** | 🎯 **Mini Project: Digit Recognizer** Recognize handwritten digits (MNIST). |

> ✅ **Result:** ML stops being scary

---

## WEEK 6: Deep Learning Foundations 🧠🔥

**Goal**
Understand CNNs intuitively.

| Learn | Tool |
| :--- | :--- |
| What CNNs do (conceptually)  | PyTorch |
| Pre-trained models | |
| Transfer learning | |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | PyTorch basics. Tensors. |
| **Day 2** | Load a pre-trained CNN. |
| **Day 3** | Classify images using a CNN. |
| **Day 4** | Fine-tune a model. |
| **Day 5** | 🎯 **Mini Project: Image Classifier** Classify everyday objects. |

> ✅ **Result:** You’re officially doing DL

---

## WEEK 7: Object Detection 🚗📦

**Goal**
Detect multiple objects in images/videos.

| Learn |
| :--- |
| Object detection vs classification |
| YOLO intuition  |

| Daily plan | Task |
| :--- | :--- |
| **Day 1** | Load YOLO model. |
| **Day 2** | Detect objects in images. |
| **Day 3** | Detect objects in video. |
| **Day 4** | Improve confidence thresholds. |
| **Day 5** | 🎯 **Mini Project: Real-Time Object Detector** Webcam object detection. |

---

## WEEK 8: Portfolio Project 🏗️

**Goal**
Build ONE project you’re proud of.

| Choose ONE |
| :--- |
| Face mask detector |
| Gesture recognition |
| Smart surveillance system |
| Object counter |

| Daily plan | Task |
| :--- | :--- |
| **Days 1–4** | Build |
| **Day 5** | Polish & document |

---

## VERY IMPORTANT RULES ⚠️

* ❌ Don’t try to understand everything
* ❌ Don’t compare yourself to YouTubers
* ❌ Don’t add new topics early
* ✔ Build ugly things
* ✔ Break code
* ✔ Be curious

---

## Final reassurance

If you follow even 70% of this plan, you’ll:
* Truly understand what CV is
* Know if you want it as a career
* Have real projects to show

* <hr><hr>


# Your 8-Week Computer Vision–First Learning Plan

| ⏱ 3 hours/day | 📅 5 days/week | **Beginner-friendly** |
| :--- | :--- | :--- |

This plan prioritizes practical building and conceptual understanding of Computer Vision (CV) over deep mathematical theory.

---

## DAILY STRUCTURE (Fixed)

| Time Slot | Activity | Focus |
| :--- | :--- | :--- |
| **45 min** | CV concept | What problem we’re solving |
| **75 min** | Coding | OpenCV / PyTorch |
| **60 min** | Mini build / experiment | Application |

> If something doesn’t click → move on anyway.

---

## WEEK 1 — Images = Numbers (CV Foundations)

| CV Goal | CV Skills Gained |
| :--- | :--- |
| Understand how computers “see” images. | Image I/O, Pixel manipulation, Coordinate system |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **What an Image Really Is** | NumPy arrays, Shape (H, W, C), `uint8` | Load image, Print pixel values, Modify a small region. **🎯 Project: Pixel modifier** |
| **Day 2** | **Colors in CV** | RGB color model, Channel splitting, Array slicing | Remove one color channel, Visualize R/G/B separately . **🎯 Project: RGB explorer** |
| **Day 3** | **Grayscale Vision** | Why grayscale is used, Weighted pixel sums, Value ranges | Convert image to grayscale, Compare RGB vs gray. **🎯 Project: Grayscale filter** |
| **Day 4** | **Image Geometry** | Image coordinates, Coordinate system, Rectangles | Draw boxes & circles, Mark objects manually. **🎯 Project: Image annotator** |
| **Day 5** | **Week Project** | **🎯 Mini Image Editor:** Load image, Grayscale, Brightness adjust, Draw shapes. |

---

## WEEK 2 — Seeing Edges & Shapes

| CV Goal |
| :--- |
| Detect structure in images. |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **Noise & Smoothing** | Noise hurts detection, Convolution (intuition only), Kernels | Blur images, Compare kernel sizes. **🎯 Blur playground** |
| **Day 2** | **Edge Detection** | Edges = intensity change, Differences, Gradients | Sobel filter, Canny edges . **🎯 Edge highlighter** |
| **Day 3** | **Binary Vision** | Separating foreground/background, Thresholding, Binary logic | Create binary images, Tune thresholds. **🎯 Document scanner** |
| **Day 4** | **Shapes & Contours** | Object boundaries, Contours, Area & perimeter | Detect shapes, Filter by size . **🎯 Shape counter** |
| **Day 5** | **Week Project** | **🎯 Shape Detection System:** Detect, Label, Count shapes. |

---

## WEEK 3 — Color, Video & Motion

| CV Goal |
| :--- |
| Process real-time video data. |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **Color Spaces** | RGB fails under lighting, HSV space, Value ranges | Color masking. **🎯 Color isolator** |
| **Day 2** | **Masking Objects** | Extract objects by color, Bitwise ops, Boolean masks | Remove background. **🎯 Color-based segmentation** |
| **Day 3** | **Video as Images** | Video = frames, Loops, Frame processing | Webcam capture, Real-time filters. **🎯 Live CV filter** |
| **Day 4** | **Motion Detection** | Detect movement, Frame differencing, Absolute difference | Motion bounding boxes. **🎯 Motion detector** |
| **Day 5** | **Week Project** | **🎯 Color Object Tracker:** Track object movement live. |

---

## WEEK 4 — Face Detection (Classic CV)

| CV Goal |
| :--- |
| Build impressive detection systems without deep learning. |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **Object Detection Basics** | Sliding windows, Feature comparison | Load Haar model, Detect faces in images . |
| **Day 2** | **Real-Time Face Detection** | Speed vs accuracy, Frame scaling | Webcam face detection. |
| **Day 3** | **Improving Detection** | False positives, Confidence thresholds | Tune detection parameters. |
| **Day 4** | **Multi-face Logic** | Multiple detections, Looping & counting | Face counter. |
| **Day 5** | **Week Project** | **🎯 Smart Face Detection App:** Detect, Count, Label faces. |

---

## WEEK 5 — Why Machine Learning Exists

| CV Goal |
| :--- |
| Understand when rule-based CV breaks. |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **ML in CV** | Pattern recognition, Features vs labels | |
| **Day 2** | **Image Classification** | Classify images, Flattening, Scaling | Digit classifier (MNIST). |
| **Day 3** | **Model Evaluation** | Accuracy & errors, Confusion matrix (intuition) | |
| **Day 4** | **Improving Models** | Overfitting, Data splitting | |
| **Day 5** | **Week Project** | **🎯 Digit Recognition App** |

---

## WEEK 6 — Deep Learning for Vision

| CV Goal |
| :--- |
| Use CNNs without drowning in theory. |

| Day | CV Concept | Needed Concepts | Build / Project |
| :--- | :--- | :--- | :--- |
| **Day 1** | **CNN Intuition** | Learn patterns automatically, Filters, Feature maps  | |
| **Day 2** | **PyTorch Basics** | Tensors instead of arrays | |
| **Day 3** | **Pretrained CNNs** | Transfer learning | Image classifier. |
| **Day 4** | **Fine-Tuning** | Improve accuracy | |
| **Day 5** | **Week Project** | **🎯 CNN Image Classifier** |

---

## WEEK 7 — Object Detection (Modern CV)

| CV Goal |
| :--- |
| Detect multiple objects in real time. |

| Day | CV Concept | Build / Project |
| :--- | :--- | :--- |
| **Day 1** | Detection vs Classification | |
| **Day 2** | YOLO Intuition | |
| **Day 3** | Image Object Detection | |
| **Day 4** | Video Object Detection | |
| **Day 5** | **Week Project** | **🎯 Real-Time Object Detector** |

---

## WEEK 8 — Portfolio Project

| CV Goal |
| :--- |
| Build something complete. |

| Choose ONE |
| :--- |
| Face mask detector |
| Gesture recognition |
| Smart surveillance |
| Object counter |

---

## Math You Will Actually Use

* ✔ Arrays & tensors
* ✔ Weighted sums
* ✔ Differences
* ✔ Boolean logic
* ✔ Coordinate geometry

* ❌ No calculus
* ❌ No proofs
* ❌ No unnecessary theory

---

## Final Reality Check

This is exactly how CV engineers learn:
> Problem → tool → concept → build

If you finish this:
* CV will make sense
* You’ll know if it’s your career
* You’ll have real projects
