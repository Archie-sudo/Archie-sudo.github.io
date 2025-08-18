document.addEventListener("DOMContentLoaded", function () {
  const form = document.getElementById("contact-form");
  const status = document.createElement("p");
  status.style.marginTop = "10px";
  form.appendChild(status);

  form.addEventListener("submit", async function (event) {
    event.preventDefault();
    status.textContent = "Sending...";

    const formData = new FormData(form);

    try {
      const response = await fetch("https://formspree.io/f/xqalovlw", {
        method: "POST",
        body: formData,
        headers: {
          Accept: "application/json",
        },
      });

      if (response.ok) {
        status.textContent = "✅ Message sent successfully!";
        form.reset();
      } else {
        status.textContent = "❌ Oops, something went wrong. Try again.";
      }
    } catch (error) {
      status.textContent = "⚠️ Network error. Please try again later.";
    }
  });
});
