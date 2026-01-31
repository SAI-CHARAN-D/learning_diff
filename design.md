# Learning Diff Bharat - Design Document

## 1. High-Level Architecture

Simple three-tier architecture focused on analyzing learner explanations and tracking understanding over time:
- **Frontend**: Web application for user interaction and explanation input
- **Backend**: API services for processing explanations and generating learning diffs
- **AI Layer**: Natural language processing and comparison algorithms
- **Storage**: User data and explanation history for temporal analysis

## 2. Major Components

### Frontend Web Application
- Clean interface for users to input explanations of technical concepts
- Progress visualization showing understanding evolution over time
- Feedback display with targeted recommendations
- Simple authentication and user management

### Backend API Services
Core services handling the learning diff functionality:
- **Explanation Processing Service**: Captures and stores user explanations
- **Analysis Engine**: Compares explanations over time to identify improvements and gaps
- **Feedback Generator**: Creates personalized recommendations based on analysis
- **User Management**: Basic authentication and profile handling

### AI Processing Components
- **NLP Analysis**: Extracts key concepts, clarity, and accuracy from explanations
- **Misconception Detection**: Identifies common errors and knowledge gaps
- **Progress Tracking**: Compares understanding depth across multiple sessions
- **Recommendation Engine**: Generates targeted feedback for improvement

### Data Storage
- **User Profiles**: Basic user information and learning preferences
- **Explanation History**: Timestamped explanations for temporal comparison
- **Analysis Results**: Processed insights and learning diff data
- **Feedback Records**: Generated recommendations and user responses

## 3. System & User Flows

### Core User Journey
1. **Initial Setup**: User creates account and selects technical topic to learn
2. **Explanation Input**: User explains concept through text input interface
3. **AI Analysis**: System processes explanation for understanding depth and accuracy
4. **Baseline Establishment**: First explanation becomes comparison baseline
5. **Progress Sessions**: User returns periodically to re-explain same concepts
6. **Diff Generation**: AI compares new explanations with previous versions
7. **Feedback Delivery**: System shows improvement areas and targeted recommendations

### Learning Diff Process
- **Concept Extraction**: AI identifies key technical concepts in explanations
- **Understanding Scoring**: Algorithm rates clarity, accuracy, and completeness
- **Temporal Comparison**: System compares scores and concepts across time periods
- **Gap Identification**: Highlights areas where understanding decreased or stagnated
- **Improvement Recognition**: Celebrates areas showing clear progress

### Feedback Loop
- User receives specific recommendations based on analysis
- System tracks which feedback leads to actual improvement
- Recommendation algorithms improve based on effectiveness data
- Users can request re-analysis after addressing feedback

## 4. AWS Integration

### Compute and Processing
- **AWS Lambda**: Serverless functions for API endpoints and explanation processing
- **Amazon SageMaker**: ML model hosting for NLP analysis and misconception detection
- **API Gateway**: Request routing and basic authentication

### Storage and Data
- **Amazon RDS**: User profiles and structured explanation metadata
- **Amazon S3**: Raw explanation text and analysis results storage
- **Amazon DynamoDB**: Session data and real-time user interactions

### AI Services
- **Amazon Comprehend**: Natural language processing for explanation analysis
- **Amazon Bedrock**: Foundation models for advanced text understanding and comparison

## 5. Technical Logic

### Explanation Analysis Algorithm
The core AI processes user explanations through multiple analysis layers:
- **Concept Identification**: Extracts technical terms and their relationships
- **Clarity Assessment**: Evaluates explanation structure and logical flow
- **Accuracy Validation**: Compares against known correct explanations
- **Completeness Scoring**: Identifies missing key concepts or steps

### Learning Diff Generation
Temporal comparison algorithm that creates meaningful learning diffs:
- **Baseline Comparison**: Measures improvement against initial explanation
- **Session-to-Session**: Tracks changes between consecutive explanations
- **Concept Evolution**: Shows how understanding of specific concepts develops
- **Regression Detection**: Identifies when understanding appears to decline

### Misconception Detection Engine
Pattern recognition system for identifying common learning errors:
- **Error Classification**: Categorizes types of misconceptions found
- **Confidence Scoring**: Rates likelihood that identified issues are actual problems
- **Context Awareness**: Considers user's learning level and background
- **Intervention Triggers**: Determines when to provide corrective feedback

### Feedback Personalization
Recommendation system that generates targeted learning suggestions:
- **Gap-Specific Advice**: Provides recommendations for identified weak areas
- **Learning Style Adaptation**: Adjusts feedback format based on user preferences
- **Progress Acknowledgment**: Celebrates improvements to maintain motivation
- **Next Steps Guidance**: Suggests specific actions for continued improvement