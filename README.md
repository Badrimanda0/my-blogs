export default function Hero() {
  return (
    <section className="w-full bg-gradient-to-r from-blue-900 to-blue-700 py-14 px-4 flex flex-col items-center">
      {/* Hero Content */}
      <div className="max-w-6xl w-full grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
        {/* Left Side Text */}
        <div>
          <h1 className="text-white text-4xl md:text-5xl font-bold leading-snug">
            Carve the Path <br />
            to a Brighter <br />
            Future with Us
          </h1>
        </div>

        {/* Right Side Semi-Circular Image */}
        <div className="flex justify-center">
          <img
            src="/hero-image.jpg" // replace with your actual image
            alt="Hero"
            className="rounded-t-full shadow-lg w-900 h-80 object-cover border-4 border-white"
          />
        </div>
      </div>

      {/* White Box Search Section */}
      <div className="bg-white justify-center shadow-lg rounded-xl mt-5 p-6 w-full max-w-6xl">
        <form className="flex justify-center flex-col gap-6">
          {/* Search Box with Icon */}
          <div className="relative max-w-xl w-full">
            <label htmlFor="job-search" className="sr-only">
              Search Jobs
            </label>
            <input
              id="job-search"
              type="text"
              placeholder="Search for jobs..."
              className="w-2xl  border rounded-lg px-1 py-2 pl-10 focus:outline-none"
            />
            {/* Search Icon (SVG) */}
            <svg
              xmlns="http://www.w3.org/2000/svg"
              className="absolute left-3 top-2.5 w-5 h-5 text-gray-500"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <circle cx="11" cy="11" r="7" strokeWidth="2" />
              <line
                x1="16.65"
                y1="16.65"
                x2="21"
                y2="21"
                strokeWidth="2"
                strokeLinecap="round"
              />
            </svg>
          </div>

          {/* Dropdowns and Button in One Row */}
          <div className="flex flex-col md:flex-row gap-4 items-center">
            {/* Experience Level Dropdown */}
            <div className="flex-1 w-full">
              <label htmlFor="experience" className="block text-sm font-medium text-gray-700 mb-1">
                Experience Level
              </label>
              <select id="experience" className="w-full border rounded-lg px-4 py-2">
                <option>All Experience Level</option>
                <option>Fresher</option>
                <option>Mid Level</option>
                <option>Senior</option>
              </select>
            </div>

            {/* Location Dropdown */}
            <div className="flex-1 w-full">
              <label htmlFor="location" className="block text-sm font-medium text-gray-700 mb-1">
                Location
              </label>
              <select id="location" className="w-full border rounded-lg px-4 py-2">
                <option>All Location</option>
                <option>Hyderabad</option>
                <option>Bangalore</option>
                <option>Delhi</option>
              </select>
            </div>

            {/* Category Dropdown */}
            <div className="flex-1 w-full">
              <label htmlFor="category" className="block text-sm font-medium text-gray-700 mb-1">
                Categories
              </label>
              <select id="category" className="w-full border rounded-lg px-4 py-2">
                <option>All Categories</option>
                <option>Development</option>
                <option>Design</option>
                <option>Marketing</option>
              </select>
            </div>

            {/* Button aligned to the right */}
            <div className="self-end md:self-center">
              <button
                type="submit"
                className="bg-blue-600 text-white px-2 py-1 rounded-lg hover:bg-blue-200"
              >
                View Jobs
              </button>
            </div>
          </div>
        </form>
      </div>
    </section>
  );
}
2nd line
// app/page.tsx
"use client";
import { useState } from "react";

const jobs = [
  {
    title: "Full Stack Developer",
    tags: ["Mid-Level", "Chennai", "Madurai"],
    shortDesc:
      "Primary Responsibility: Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular. Building and maintaining server-side application logic, databases...",
    details: {
      responsibility: `Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular. Building and maintaining server-side application logic, databases, and APIs using technologies such as Node.js, Python, Ruby, or Java. Designing, implementing, and managing databases (SQL or NoSQL) to ensure data integrity and efficient retrieval. Using version control systems (Git) to manage code changes and collaborate with other developers. Implementing security best practices to protect applications from vulnerabilities and threats. Automating development processes and managing CI/CD pipelines to streamline deployment and release cycles. Working with cross-functional teams, including designers, product managers, and other developers, to deliver high-quality software.`,
      specification: [
        "Proficiency in front-end technologies HTML, CSS, JavaScript frameworks like React or Angular.",
        "Proficiency in back-end technologies Node.js, Python, Ruby, Java, etc.",
        "Experience in designing and managing databases (SQL and NoSQL).",
        "Proficiency in schema design and query optimization.",
        "Strong knowledge of version control systems, particularly Git.",
        "Expertise in managing and collaborating on code repositories.",
        "Knowledge of web security best practices.",
        "Experience with performance optimization techniques.",
        "Excellent collaboration skills for working effectively in a team environment.",
        "Ability to communicate technical concepts to non-technical stakeholders.",
      ],
      type: "Full-time",
      mode: "Hybrid",
      salary: "Industry standard",
      experience: "Minimum 3 years",
      location: "Chennai, Madurai, Coimbatore",
    },
  },
  {
    title: "React Developer",
    tags: ["Mid-Level", "Chennai", "Madurai"],
    shortDesc:
      "Primary Responsibility: Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular...",
    details: null,
  },
  {
    title: "Flutter Developer",
    tags: ["Mid-Level", "Chennai", "Madurai"],
    shortDesc:
      "Primary Responsibility: Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular...",
    details: null,
  },
  {
    title: "Php Developer",
    tags: ["Mid-Level", "Chennai", "Madurai"],
    shortDesc:
      "Primary Responsibility: Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular...",
    details: null,
  },
  {
    title: "Mern Stack Developer",
    tags: ["Mid-Level", "Chennai", "Madurai"],
    shortDesc:
      "Primary Responsibility: Designing and implementing user interfaces using HTML, CSS, and JavaScript frameworks like React or Angular...",
    details: null,
  },
];

export default function JobPortal() {
  const [selectedJob, setSelectedJob] = useState(jobs[0]);

  return (
    <main className="min-h-screen bg-white p-6 flex justify-center">
      <div className="max-w-6xl w-full grid grid-cols-1 md:grid-cols-2 gap-6">
        
        {/* Left Panel (Job List) */}
        <div className="space-y-4">
          {jobs.map((job, idx) => (
            <div
              key={idx}
              onClick={() => setSelectedJob(job)}
              className={`p-4 border rounded-lg cursor-pointer transition ${
                selectedJob.title === job.title
                  ? "border-blue-600 bg-blue-50"
                  : "border-gray-300 bg-gray-100 hover:bg-gray-200"
              }`}
            >
              <h3 className="text-lg font-bold text-blue-900">{job.title}</h3>
              <div className="flex gap-2 my-2 flex-wrap">
                {job.tags.map((tag, i) => (
                  <span
                    key={i}
                    className="text-xs bg-gray-200 px-2 py-1 rounded-md"
                  >
                    {tag}
                  </span>
                ))}
              </div>
              <p className="text-sm text-gray-600 line-clamp-2">
                {job.shortDesc}
              </p>
            </div>
          ))}
        </div>

        {/* Right Panel (Job Details) */}
        <div className="border rounded-lg p-6 shadow-sm flex flex-col">
          {selectedJob.details ? (
            <>
              <div className="flex-1 overflow-y-auto">
                <h2 className="text-xl font-bold text-blue-900">
                  {selectedJob.title}
                </h2>
                <div className="flex gap-2 my-2 flex-wrap">
                  {selectedJob.tags.map((tag, i) => (
                    <span
                      key={i}
                      className="text-xs bg-gray-200 px-2 py-1 rounded-md"
                    >
                      {tag}
                    </span>
                  ))}
                </div>

                <h3 className="font-semibold mt-4">Primary Responsibility:</h3>
                <p className="text-sm text-gray-700 mt-2 leading-relaxed">
                  {selectedJob.details.responsibility}
                </p>

                <h3 className="font-semibold mt-4">Job Specification:</h3>
                <ul className="list-disc list-inside text-sm text-gray-700 mt-2 space-y-1">
                  {selectedJob.details.specification.map((spec, i) => (
                    <li key={i}>{spec}</li>
                  ))}
                </ul>

                <div className="mt-4 text-sm text-gray-700 space-y-1">
                  <p>
                    <strong>Employment Type:</strong>{" "}
                    {selectedJob.details.type}
                  </p>
                  <p>
                    <strong>Workplace Type:</strong> {selectedJob.details.mode}
                  </p>
                  <p>
                    <strong>Salary:</strong> {selectedJob.details.salary}
                  </p>
                  <p>
                    <strong>Experience Required:</strong>{" "}
                    {selectedJob.details.experience}
                  </p>
                  <p>
                    <strong>Job Location:</strong>{" "}
                    {selectedJob.details.location}
                  </p>
                </div>
              </div>

              {/* Apply Now Button Inside */}
              <div className="mt-6 justify-center">
                <button className="w-40 bg-blue-600 text-white py-3 rounded-lg font-semibold hover:bg-blue-700 transition">
                  Apply Now
                </button>
              </div>
            </>
          ) : (
            <p className="text-gray-500">
              Select a job from the left panel to view details.
            </p>
          )}
        </div>
      </div>
    </main>
  );
}
export default function CTASection() {
  return (
    <section className="w-full bg-gradient-to-r from-blue-900 to-blue-800 py-20 text-center text-white">
      <h2 className="text-3xl font-bold mb-4">Let's Work Together</h2>
      <p className="max-w-2xl mx-auto text-sm md:text-base mb-6">
        Great minds don’t just think alike—they work together! Join us and turn ambition into action.
      </p>
      <button className="bg-white text-blue-600 px-6 py-2 rounded-lg font-semibold hover:bg-gray-100 transition">
        Ask us any Questions
      </button>
    </section>
  );
}
