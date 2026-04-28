// Autohaus Ostbevern - Vanilla JS

document.addEventListener('DOMContentLoaded', () => {
  // Update copyright year
  const copyright = document.getElementById('copyright');
  if (copyright) {
    copyright.textContent = `© ${new Date().getFullYear()} Autohaus Ostbevern GmbH. Alle Rechte vorbehalten.`;
  }

  // Scroll-to-top CTA button
  const scrollBtn = document.getElementById('scroll-top-btn');
  if (scrollBtn) {
    scrollBtn.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });
  }

  // Contact form handler (mailto fallback - no backend needed)
  const form = document.getElementById('contact-form');
  if (form) {
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      const data = new FormData(form);
      const name = data.get('name');
      const phone = data.get('phone');
      const email = data.get('email') || '';
      const message = data.get('message');

      const subject = encodeURIComponent(`Anfrage von ${name}`);
      const body = encodeURIComponent(
        `Name: ${name}\nTelefon: ${phone}\nE-Mail: ${email}\n\nNachricht:\n${message}`
      );

      // Open user's email client with prefilled message
      window.location.href = `mailto:info@autohaus-ostbevern.de?subject=${subject}&body=${body}`;

      showToast('Vielen Dank! Ihr E-Mail-Programm öffnet sich jetzt.', 'success');
      form.reset();
    });
  }

  // Fade-in on scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.card, .reason, .gallery-item, .faq-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(20px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });
});

function showToast(message, type = 'success') {
  const toast = document.getElementById('toast');
  if (!toast) return;
  toast.textContent = message;
  toast.className = `toast show ${type}`;
  setTimeout(() => { toast.className = 'toast'; }, 4000);
}
