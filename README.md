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

### **TF-IDF Vectorization**
Converts article text into numerical vectors.

```python
vectorizer = TfidfVectorizer(stop_words="english", max_features=5000)
X = vectorizer.fit_transform(df["text"])
