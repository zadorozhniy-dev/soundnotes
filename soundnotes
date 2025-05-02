// Check if there are any notes stored in localStorage
const notes = JSON.parse(localStorage.getItem('soundNotes')) || [];

// Select DOM elements
const form = document.getElementById('note-form');
const titleInput = document.getElementById('title');
const lyricsInput = document.getElementById('lyrics');
const chordsInput = document.getElementById('chords');
const bpmInput = document.getElementById('bpm');
const moodInput = document.getElementById('mood');
const notesList = document.getElementById('notes-list');

// Function to render notes on the page
function renderNotes() {
  notesList.innerHTML = ''; // Clear the list first
  notes.forEach((note, index) => {
    const noteDiv = document.createElement('div');
    noteDiv.classList.add('note');

    noteDiv.innerHTML = `
      <h3>${note.title}</h3>
      <p><strong>Chords:</strong> ${note.chords}</p>
      <p><strong>Lyrics:</strong> ${note.lyrics}</p>
      <p><strong>BPM:</strong> ${note.bpm}</p>
      <p><strong>Mood:</strong> ${note.mood}</p>
      <button class="delete-btn" onclick="deleteNote(${index})">Delete</button>
    `;
    notesList.appendChild(noteDiv);
  });
}

// Function to delete a note
function deleteNote(index) {
  notes.splice(index, 1); // Remove the note from the array
  localStorage.setItem('soundNotes', JSON.stringify(notes)); // Save updated notes to localStorage
  renderNotes(); // Re-render the list
}

// Form submission handler
form.addEventListener('submit', (event) => {
  event.preventDefault(); // Prevent form from submitting normally

  const newNote = {
    title: titleInput.value,
    lyrics: lyricsInput.value,
    chords: chordsInput.value,
    bpm: bpmInput.value,
    mood: moodInput.value,
  };

  notes.push(newNote); // Add the new note to the array
  localStorage.setItem('soundNotes', JSON.stringify(notes)); // Save the notes to localStorage
  renderNotes(); // Re-render the list

  // Clear the form fields
  titleInput.value = '';
  lyricsInput.value = '';
  chordsInput.value = '';
  bpmInput.value = '';
  moodInput.value = '';
});

// Initialize the notes display on page load
renderNotes();
