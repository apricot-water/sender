self.addEventListener('push', function(event) {
  // Nachricht empfangen
  let data = {};
  if (event.data) {
    try {
      data = event.data.json();
    } catch(e) {
      // Falls kein JSON, nehmen wir Text
      data = { message: event.data.text() };
    }
  }

  const title = "Familien Chat";
  // Wir zeigen eine generische Nachricht, da wir hier keinen Key zum Entschlüsseln haben
  const options = {
    body: "Neue Nachricht eingegangen! 📩", 
    icon: "icon-192.png",
    badge: "icon-192.png",
    vibrate: [200, 100, 200]
  };

  event.waitUntil(
    self.registration.showNotification(title, options)
  );
});


    self.addEventListener('notificationclick', function(event) {
  event.notification.close();
  // KORREKTUR: Auf index.html oder ./ leiten, nicht sender.html
  event.waitUntil(
    clients.openWindow('./') 
  );
});
