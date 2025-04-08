import telebot
import time

# Telegram Bot Token ve Kanal Kullanıcı Adı
API_TOKEN = '7763681544:AAGc83LUyj-gyZ2fNsYfRRclGc_mLS-OEqc '
CHANNEL_USERNAME = '@TarihiBilgiler'

# Telegram botunu başlatma
bot = telebot.TeleBot(API_TOKEN)

# Günlük mesajı gönderecek fonksiyon
def send_daily_report():
    report = """Bugünün Raporu:
    1. Türk Tarihi: ...
    2. Askerî Strateji: ...
    3. Özlü Söz: "Türk'ün gücü, milliyetinden gelir."
    """
    bot.send_message(CHANNEL_USERNAME, report)

# Her gün sabah 8:00'de mesaj gönderme
while True:
    # Saat kontrolü (08:00'de mesaj gönder)
    current_time = time.localtime()
    if current_time.tm_hour == 8 and current_time.tm_min == 0:
        send_daily_report()
    time.sleep(60)  # Her dakika kontrol et
