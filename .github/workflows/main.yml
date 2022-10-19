
import os
import re
from youtube_dl import YoutubeDL
ydl_opts = {
    "geo-bypass": True,
    "nocheckcertificate": True
    }
ydl = YoutubeDL(ydl_opts)
links=[]
finalurl=""
STREAM=os.environ.get("STREAM_URL", "https://www.liveradio.ie/stations/star-radio-tamil")
regex = r"^(https?\:\/\/)?(www\.youtube\.com|youtu\.?be)\/.+"
match = re.match(regex,STREAM)
if match:
    meta = ydl.extract_info(STREAM, download=False)
    formats = meta.get('formats', [meta])
    for f in formats:
        links.append(f['url'])
    finalurl=links[0]
else:
    finalurl=STREAM

class Config:
    ADMIN = os.environ.get("ADMINS", '')
    ADMINS = [int(admin) if re.search('^\d+$', admin) else admin for admin in (ADMIN).split()]
    API_ID = int(os.environ.get("API_ID", '10670890'))
    CHAT = int(os.environ.get("CHAT", "-1001768257900"))
    LOG_GROUP=os.environ.get("LOG_GROUP", "-1001768257900")
    if LOG_GROUP:
        LOG_GROUP=int(LOG_GROUP)
    else:
        LOG_GROUP=None
    STREAM_URL=finalurl
    ADMIN_ONLY=os.environ.get("ADMIN_ONLY", "Y")
    DURATION_LIMIT=int(os.environ.get("DUR", 1500))
    API_HASH = os.environ.get("API_HASH", "b8c18624a9a4b397e9989c30904de9d2")
    BOT_TOKEN = os.environ.get("BOT_TOKEN", "5483191761:AAFBHL5pIvS-rZHLskHuk3SgvLY6o0bN5I4") 
    SESSION = os.environ.get("SESSION_STRING", "BABy3cy3eKp-UkHtUEsQujJsAtnJTTIk1E5DTCFEI10WW_WPOax1H7S43Eqs-SfIo2Dez_iCFDA62GyqjP_P1mbLJdnQIXnxUI11RZ4bimilVb0lNcA-EWV8skTa_Sy3pR3eVWJe91jG1_3zQzCZwBQdF64LlHJkMlNN3AQteyksdczVGJRPU9yd_AnN__YP63nWNi159Pz2PTaMTWY82gpS9GuHDHhZbPt3i5ddey6BiJRLibiJeFF96r8yDvlTTD3m4KclaQcadAicAsPaflQhmsAU6p3kHw-szUpD7GTfYFwUh2bhS7ZYoTN4-kSgZTVkpSuXbKZYKg-M3Ks0lUEPdW1H7gA")
    DOWNLOAD_LOCATION = os.environ.get("DOWNLOAD_LOCATION", "./DOWNLOADS/")
    playlist=[]
    msg = {}
