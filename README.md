# AI News Recommendation System

An AI-driven news recommendation system that uses NLP (TF-IDF), cosine similarity, and user behavior modeling to deliver personalized article recommendations.  
Users can read articles, upvote/downvote them, and interact with a clean, modern Streamlit UI that re-ranks recommendations in real time.

---

## 📌 Features

### 1. **AI-Powered Content Recommendations**
- Computes similarity between articles using **TF-IDF** and **cosine similarity**.
- Recommends articles based on textual relevance.

### 2. **Behavior-Driven Personalization**
- User likes/dislikes influence ranking.
- Reading behavior stored in session state.
- Hybrid recommendation = similarity + behavior weights.

### 3. **Interactive Reading Mode**
- Opens article in a sidebar pane.
- Includes Like / Downvote buttons.
- Fully scrollable reading view.

### 4. **Paginated Article Feed**
- Shows articles in batches of 10.
- Shuffled dataset ensures category variety.
- Clean card-style UI layout.

### 5. **Modern Streamlit UI**
- Styled buttons (green = Like, red = Downvote, blue = Read)
- Word-wrap handling for long text
- Responsive card layout

### 6. **ML/NLP Ready Architecture**
Designed for easy extension with:
- SHAP explainability
- Text classification (Logistic Regression / BERT)
- Topic modeling
- Behavioral analytics dashboard
- Fairness and Responsible AI checks

---

## 🧠 How It Works

### Dataset Loading
The dataset (`bbc-news-data.json`) contains:
* category  
* title  
* filename  
* content (renamed to `text`)

Data is cleaned and indexed before vectorization.

---

### TF-IDF Vectorization
* Converts article text into numerical vectors  
* Captures term importance across corpus  
* Uses a 5000-feature limit for efficiency  

TF-IDF provides the base representation for similarity scoring.

---

### Cosine Similarity Matrix
* Computes similarity between every article pair  
* Higher score = more similar content  
* Used to rank recommendations before behavior weighting  

This matrix powers the ML side of the recommender.

---

###  Behavioral Tracking (User Interactions)
The app tracks:
* Likes (upvotes)  
* Dislikes (downvotes)  
* Reading activity  
* Current page  
* Current selected article  

Behavior is stored using Streamlit session state.

This allows:
* Dynamic personalization  
* Voting-based ranking  
* A hybrid recommendation flow  

---

### Hybrid Recommendation Logic
The system combines:
* TF-IDF similarity  
* Vote-based weighting  
* Weighted randomization  
* Deduplication  
* Guaranteed inclusion of highest-voted item  

Final top-3 recommendations are:
1. Personalized  
2. Diverse  
3. Real-time reactive  

---

### Streamlit Interface Architecture
The app contains three main UI sections:

#### **Top 3 Recommended Articles**
* Dynamically updated  
* Shows title, category, preview  
* Includes Like / Downvote / Read buttons  
* Buttons use session-based callbacks  

#### **More Articles (Paginated)**
* Displays 10 articles per page  
* Dataset shuffled at startup for category variance  
* Page navigation: Previous / Next  
* Each card includes:
  * Title  
  * Category  
  * Preview text  
  * Action buttons  

#### **Reading Mode Sidebar**
Activated when “Read” is clicked.
Shows:
* Full article text  
* Title  
* Category  
* Like / Downvote buttons  
* Auto-scroll compatible layout  

---

## 🗂️ Folder Structure

| File | Description |
|------|-------------|
| `app.py` | Main Streamlit application |
| `bbc-news-data.json` | BBC News dataset used for recommendations |
| `requirements.txt` | All required Python libraries |
| `README.md` | Project documentation |

---

## ▶️ Run the Application

### #### 1. Clone the Repository
> Run the following:
> ```bash
> git clone https://github.com/your-username/ai-news-recommender.git
> cd ai-news-recommender
> ```

#### 2. Install Dependencies
> ```bash
> pip install -r requirements.txt
> ```
#### 3. Start the Application

> ```bash
> streamlit run app.py
> ```
#### 4. Access in Browser
Streamlit will open automatically

If not, visit:

http://localhost:8501
