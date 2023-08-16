# Pandas-challenge
Challenge assignment for Pandas 

In this challenge, I utilized the formatting and sample code for the provided starter code throughout, adding sections and sub-sections for clarity.

I kept many of the same or similar names for dataframes/sections to the starter code provided

Some larger specifically used sections in guide listed below with some renaming:

--------------------------------------------------
Percent Passing Math/Reading/Both
--------------------------------------------------

passing_math_reading_count = combined_school_df[
    (combined_school_df["math_score"] >= 70) & (combined_school_df["reading_score"] >= 70)
].count()["student_name"]
passing_math_reading_count

overall_passing_rate = passing_math_reading_count /  float(students_count) * 100
overall_passing_rate

--------------------------------------------------
Scores by School Spending
--------------------------------------------------

spending_bins = [0, 585, 630, 645, 680]
labels = ["<$585", "$585-630", "$630-645", "$645-680"]

spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

--------------------------------------------------
Scores by School Size
--------------------------------------------------

size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]


--------------------------------------------------
Scores by Grade
--------------------------------------------------

ninth_graders_df = combined_school_df[(combined_school_df["grade"] == "9th")]
tenth_graders_df = combined_school_df[(combined_school_df["grade"] == "10th")]
eleventh_graders_df = combined_school_df[(combined_school_df["grade"] == "11th")]
twelfth_graders_df = combined_school_df[(combined_school_df["grade"] == "12th")]

ninth_grade_math_scores_df = ninth_graders_df.groupby(["school_name"])["math_score"].mean()
tenth_grader_math_scores_df = tenth_graders_df.groupby(["school_name"])["math_score"].mean()
eleventh_grader_math_scores_df = eleventh_graders_df.groupby(["school_name"])["math_score"].mean()
twelfth_grader_math_scores_df = twelfth_graders_df.groupby(["school_name"])["math_score"].mean()

