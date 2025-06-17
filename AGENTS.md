# Overview of Agents in Teacher Repository

This document outlines the LLM-based and autonomous agents used within the Teacher project. It serves as a reference for contributors and AI tooling, detailing the roles, triggers, behaviors, and outputs of each agent.

## Table of Agents

| Name              | Description                                     | Trigger                             |
|-------------------|-------------------------------------------------|-------------------------------------|
| CourseGenerator    | Generates course outlines based on input parameters | Command: `generate-course`          |
| ChapterCreator     | Creates new chapters for courses               | Command: `create-chapter`          |
| AnalyticsReporter   | Generates analytics reports for courses         | CI event: `generate-analytics`      |

## Detailed Breakdown of Each Agent

### CourseGenerator

**Description:**  
The CourseGenerator agent is responsible for creating course outlines based on specified parameters such as topic, duration, and target audience.

**Trigger:**  
- Command: `generate-course`

**Inputs:**  
- Topic: String  
- Duration: Integer (in weeks)  
- Target Audience: String  

**Outputs:**  
- Course Outline: JSON object containing course structure  

**Where the Logic Lives:**  
- `/agents/course-generator.ts`

**Review/Audit Process:**  
- Manual review by course creators before finalizing the course outline.

### ChapterCreator

**Description:**  
The ChapterCreator agent automates the creation of new chapters within a course, ensuring consistency and structure.

**Trigger:**  
- Command: `create-chapter`

**Inputs:**  
- Course ID: String  
- Chapter Title: String  
- Chapter Content: String  

**Outputs:**  
- New Chapter: JSON object representing the new chapter  

**Where the Logic Lives:**  
- `/agents/chapter-creator.ts`

**Review/Audit Process:**  
- Automated checks for content quality and manual review by course instructors.

### AnalyticsReporter

**Description:**  
The AnalyticsReporter agent compiles and generates analytics reports for courses, providing insights into student engagement and performance.

**Trigger:**  
- CI event: `generate-analytics`

**Inputs:**  
- Course ID: String  
- Time Period: String (e.g., "last month")  

**Outputs:**  
- Analytics Report: PDF document with charts and statistics  

**Where the Logic Lives:**  
- `/agents/analytics-reporter.ts`

**Review/Audit Process:**  
- Automated validation of data accuracy and manual review by analytics team.

## How to Invoke Each Agent

### CourseGenerator
- **CLI:** Run `npm run generate-course -- --topic="Web Development" --duration=8 --audience="Beginners"`
- **CI:** Trigger the `generate-course` workflow in the CI pipeline.

### ChapterCreator
- **CLI:** Run `npm run create-chapter -- --courseId="course123" --title="Introduction" --content="This chapter introduces..."`
- **CI:** Trigger the `create-chapter` workflow in the CI pipeline.

### AnalyticsReporter
- **CLI:** Not applicable
- **CI:** Trigger the `generate-analytics` workflow in the CI pipeline.

## Future Agent Proposals

- **FeedbackAnalyzer:** An agent that analyzes student feedback to improve course content.
- **ContentOptimizer:** An agent that optimizes course content for better engagement and learning outcomes.

## Contribution Instructions for New Agents

To contribute a new agent to the Teacher project, follow these steps:

1. **Develop the Agent:** Write the agent logic in TypeScript and place it in the `/agents` directory.
2. **Document the Agent:** Add a detailed entry to this `AGENTS.md` file under the "Detailed Breakdown of Each Agent" section.
3. **Test the Agent:** Ensure the agent works as expected and passes all relevant tests.
4. **Submit a Pull Request:** Open a pull request with your changes, including the new agent code and documentation updates.
