#!/usr/bin/env python3
"""
README Generator for Pratiksha Tripathi - Data Science Student
This script creates a professional README.md file for GitHub profile or projects.
"""

import datetime
import os

def generate_readme():
    """Generate a comprehensive README for a data science student"""
    
    # Get current year for copyright or date information
    current_year = datetime.datetime.now().year
    
    # Collect user information
    print("=" * 50)
    print("README Generator for Pratiksha Tripathi")
    print("=" * 50)
    print("\nPlease provide the following information:")
    
    # Basic information
    name = "Pratiksha Tripathi"
    title = "Data Science Student"
    location = input("Your location (e.g., City, Country): ").strip()
    email = input("Your email address: ").strip()
    linkedin = input("Your LinkedIn profile URL: ").strip()
    github = input("Your GitHub username: ").strip()
    portfolio = input("Your portfolio website (if any): ").strip()
    
    # About section
    print("\nNow let's create your 'About Me' section:")
    about_me = input("Describe yourself in 2-3 sentences:\n").strip()
    
    # Education
    print("\nEducation Information:")
    university = input("University name: ").strip()
    degree = input("Degree program: ").strip()
    graduation_year = input("Expected graduation year: ").strip()
    relevant_courses = input("List relevant courses (comma-separated): ").strip()
    
    # Skills
    print("\nTechnical Skills:")
    programming_langs = input("Programming languages (comma-separated): ").strip()
    data_science_tools = input("Data Science tools/libraries (comma-separated): ").strip()
    databases = input("Databases (comma-separated): ").strip()
    visualization_tools = input("Visualization tools (comma-separated): ").strip()
    cloud_tools = input("Cloud platforms/tools (comma-separated): ").strip()
    
    # Projects
    projects = []
    print("\nNow let's add some projects (enter 'done' when finished):")
    while True:
        project_name = input("\nProject name (or 'done' to finish): ").strip()
        if project_name.lower() == 'done':
            break
        project_desc = input("Project description: ").strip()
        project_tech = input("Technologies used: ").strip()
        project_link = input("GitHub/project link: ").strip()
        
        projects.append({
            'name': project_name,
            'description': project_desc,
            'technologies': project_tech,
            'link': project_link
        })
    
    # Work Experience (optional)
    experience = []
    print("\nAdd work experience/internships (enter 'done' when finished):")
    while True:
        job_title = input("\nJob title (or 'done' to finish): ").strip()
        if job_title.lower() == 'done':
            break
        company = input("Company name: ").strip()
        duration = input("Duration (e.g., May 2023 - August 2023): ").strip()
        job_desc = input("Description of responsibilities: ").strip()
        
        experience.append({
            'title': job_title,
            'company': company,
            'duration': duration,
            'description': job_desc
        })
    
    # Certifications & Achievements
    certifications = []
    print("\nAdd certifications or achievements (enter 'done' when finished):")
    while True:
        cert_name = input("\nCertification/Achievement (or 'done' to finish): ").strip()
        if cert_name.lower() == 'done':
            break
        cert_org = input("Issuing organization: ").strip()
        cert_date = input("Date earned: ").strip()
        
        certifications.append({
            'name': cert_name,
            'organization': cert_org,
            'date': cert_date
        })
    
    # Generate the README content
    readme_content = f"""# Hi there, I'm {name} 👋

{about_me}

## 🎓 Education
- **{degree}** at {university} (Expected {graduation_year})
- Relevant Courses: {relevant_courses}

## 🔧 Technical Skills
- **Programming Languages:** {programming_langs}
- **Data Science & ML Libraries:** {data_science_tools}
- **Databases:** {databases}
- **Data Visualization:** {visualization_tools}
- **Cloud Platforms:** {cloud_tools}

## 🚀 Projects

"""

    # Add projects
    for i, project in enumerate(projects, 1):
        readme_content += f"""### {i}. {project['name']}
{project['description']}

**Technologies used:** {project['technologies']}  
**Link:** [{project['name']}]({project['link']})

"""
    
    # Add experience if any
    if experience:
        readme_content += "## 💼 Experience\n\n"
        for exp in experience:
            readme_content += f"""### {exp['title']} at {exp['company']}
**{exp['duration']}**  
{exp['description']}

"""
    
    # Add certifications if any
    if certifications:
        readme_content += "## 📜 Certifications & Achievements\n\n"
        for cert in certifications:
            readme_content += f"- **{cert['name']}** from {cert['organization']} ({cert['date']})\n"
        readme_content += "\n"
    
    # Add contact information
    readme_content += f"""## 📫 Contact Me

- Email: {email}
- LinkedIn: [{linkedin}]({linkedin})
- GitHub: [{github}](https://github.com/{github})
"""
    
    if portfolio:
        readme_content += f"- Portfolio: [{portfolio}]({portfolio})\n"
    
    # Add footer
    readme_content += f"""
---

⭐️ From [{name}](https://github.com/{github})
"""

    # Write to file
    filename = "README.md"
    with open(filename, "w") as file:
        file.write(readme_content)
    
    print(f"\n✅ README.md has been generated successfully!")
    print(f"📁 File saved as: {os.path.abspath(filename)}")
    print("\nRemember to:")
    print("1. Review and customize the content")
    print("2. Add any additional sections you need")
    print("3. Update it regularly as you learn new skills and complete new projects!")

if __name__ == "__main__":
    generate_readme()
