# CEO
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>School Portal</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>School Portal</h1>
    <nav>
      <ul>
        <li><a href="#grades">Grade Calculator</a></li>
        <li><a href="#vote">Student Voting</a></li>
      </ul>
    </nav>
  </header>

  <section id="grades">
    <h2>Grade Calculator</h2>
    <form id="gradeForm">
      <label for="score">Enter your score (%):</label>
      <input type="number" id="score" min="0" max="100" required>
      <button type="submit">Calculate Grade</button>
    </form>
    <p id="gradeResult"></p>
  </section>

  <section id="vote">
    <h2>Vote for Student Leader</h2>
    <form id="voteForm">
      <label for="school">Select your school:</label>
      <select id="school" required>
        <option value="">--Choose School--</option>
        <option value="Science">Science School</option>
        <option value="Arts">Arts School</option>
        <option value="Business">Business School</option>
      </select>

      <label for="student">Select a student:</label>
      <select id="student" required>
        <option value="">--Choose Student--</option>
        <option value="Chidera">Chidera</option>
        <option value="Chikachi">Chikachi</option>
        <option value="Charis">Charis</option>
        <option value="Lesta">Lesta</option>
        <option value="Jonas">Jonas</option>
        <option value="Benard">Benard</option>
        <option value="Chisom">Chisom</option>
        <option value="Beastmark">Beastmark</option>
        <option value="Joshua">Joshua</option>
        <option value="Peter">Peter</option>
      </select>

      <button type="submit">Vote</button>
    </form>
    <p id="voteResult"></p>
  </section>

  <footer>
    <p>&copy; 2026 School Portal</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f4f4f4;
  color: #333;
}

header {
  background: #222;
  color: #fff;
  padding: 1rem;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
}

nav ul li a {
  color: #fff;
  text-decoration: none;
}

section {
  padding: 2rem;
  background: #fff;
  margin: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

form {
  display: flex;
  flex-direction: column;
  max-width: 400px;
}

form label {
  margin-top: 10px;
}

form input, form select {
  padding: 8px;
  margin-top: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

form button {
  margin-top: 15px;
  padding: 10px;
  background: #222;
  color: #fff;
  border: none;
  cursor: pointer;
}

form button:hover {
  background: #444;
}
// Grade Calculator
document.getElementById("gradeForm").addEventListener("submit", function(event) {
  event.preventDefault();
  const score = parseInt(document.getElementById("score").value);
  let grade;

  if (score >= 80) grade = "A";
  else if (score >= 70) grade = "B";
  else if (score >= 60) grade = "C";
  else if (score >= 50) grade = "D";
  else grade = "F";

  document.getElementById("gradeResult").textContent =
    `Your grade is: ${grade}`;
});

// Voting System
document.getElementById("voteForm").addEventListener("submit", function(event) {
  event.preventDefault();
  const school = document.getElementById("school").value;
  const student = document.getElementById("student").value;

  if (school && student) {
    document.getElementById("voteResult").textContent =
      `You voted for ${student} from ${school} School.`;
  } else {
    document.getElementById("voteResult").textContent =
      "Please select both school and student.";
  }
});
