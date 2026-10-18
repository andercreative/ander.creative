<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI Creative &amp; Marketing Toolkit — @ander.creative Notion Doc</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.1/dist/chart.umd.min.js"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Plus+Jakarta+Sans:wght@600;700;800&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'system-ui', '-apple-system', 'sans-serif'],
            display: ['Plus Jakarta Sans', 'Inter', 'sans-serif'],
            mono: ['JetBrains Mono', 'monospace']
          },
          colors: {
            brand: {
              paper: '#FAF8F5',
              card: '#FFFFFF',
              ink: '#181D24',
              slate: '#475569',
              orange: '#F97316',
              orangeDark: '#EA580C',
              orangeSoft: '#FFF7ED',
              periwinkle: '#CFDDF0',
              periwinkleSoft: '#EFF4FB',
              sage: '#15803D',
              sageSoft: '#F0FDF4',
              charcoal: '#1E242B'
            }
          }
        }
      }
    };
  </script>
  <style>
    :root {
      --bg-page: #FAF8F5;
      --bg-card: #FFFFFF;
      --bg-subtle: #F3F1EC;
      --border-soft: #E5E0D8;
      --text-main: #181D24;
      --text-secondary: #475569;
      --accent-orange: #EA580C;
      --accent-sage: #15803D;
    }

    html.dark {
      --bg-page: #181B20;
      --bg-card: #21262D;
      --bg-subtle: #282E37;
      --border-soft: #363E4A;
      --text-main: #F8FAFC;
      --text-secondary: #CBD5E1;
    }

    body {
      background-color: var(--bg-page);
      color: var(--text-main);
      font-family: 'Inter', system-ui, -apple-system, sans-serif;
      line-height: 1.65;
      overflow-x: hidden;
      transition: background-color 0.2s ease, color 0.2s ease;
    }

    /* Iridescent Periwinkle-Pearl Notion Cover inspired by the new TikTok profile pic */
    .notion-cover-banner {
      background:
        radial-gradient(circle at 20% 30%, rgba(255, 255, 255, 0.85) 0%, transparent 45%),
        radial-gradient(circle at 80% 25%, rgba(255, 180, 130, 0.35) 0%, transparent 40%),
        linear-gradient(125deg, #B8CCE4 0%, #D9E4F2 35%, #EBF1F8 65%, #C9D8EC 100%);
      border-bottom: 1px solid rgba(148, 163, 184, 0.3);
    }

    html.dark .notion-cover-banner {
      background:
        radial-gradient(circle at 20% 30%, rgba(249, 115, 22, 0.2) 0%, transparent 45%),
        linear-gradient(125deg, #1E293B 0%, #273549 50%, #1E242B 100%);
      border-bottom: 1px solid #363E4A;
    }

    /* Clean tactile Notion Document cards (no generic AI neon glow) */
    .doc-card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-soft);
      border-radius: 16px;
      box-shadow: 0 2px 8px rgba(24, 29, 36, 0.04);
      transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease;
    }

    .doc-card:hover {
      border-color: #CBD5E1;
      box-shadow: 0 8px 24px rgba(24, 29, 36, 0.07);
    }

    html.dark .doc-card:hover {
      border-color: #64748B;
    }

    /* Notion Callout Blocks */
    .notion-callout-warm {
      background-color: #FFF7ED;
      border: 1px solid #FED7AA;
      border-left: 4px solid #F97316;
      border-radius: 12px;
      color: #1E242B;
    }

    html.dark .notion-callout-warm {
      background-color: rgba(249, 115, 22, 0.12);
      border-color: rgba(249, 115, 22, 0.35);
      border-left: 4px solid #F97316;
      color: #F8FAFC;
    }

    .notion-callout-sage {
      background-color: #F0FDF4;
      border: 1px solid #BBF7D0;
      border-left: 4px solid #16A34A;
      border-radius: 12px;
      color: #1E242B;
    }

    html.dark .notion-callout-sage {
      background-color: rgba(22, 163, 74, 0.12);
      border-color: rgba(22, 163, 74, 0.35);
      border-left: 4px solid #22C55E;
      color: #F8FAFC;
    }

    .notion-callout-blue {
      background-color: #EFF6FF;
      border: 1px solid #BFDBFE;
      border-left: 4px solid #2563EB;
      border-radius: 12px;
      color: #1E242B;
    }

    html.dark .notion-callout-blue {
      background-color: rgba(59, 130, 246, 0.12);
      border-color: rgba(59, 130, 246, 0.35);
      border-left: 4px solid #60A5FA;
      color: #F8FAFC;
    }

    /* Character Illustration Frame */
    .char-sticker-frame {
      background-color: #1E242B;
      border: 3px solid #FFFFFF;
      box-shadow: 0 6px 16px rgba(24, 29, 36, 0.12);
      border-radius: 14px;
      overflow: hidden;
    }

    /* Primary Tangerine Button */
    .btn-primary-orange {
      background-color: #EA580C;
      color: #FFFFFF;
      font-weight: 600;
      transition: all 0.18s ease;
      box-shadow: 0 2px 6px rgba(234, 88, 12, 0.25);
    }

    .btn-primary-orange:hover {
      background-color: #C2410C;
      transform: translateY(-1px);
      box-shadow: 0 4px 12px rgba(234, 88, 12, 0.35);
    }

    /* Secondary Tactile Button */
    .btn-secondary-doc {
      background-color: var(--bg-subtle);
      border: 1px solid var(--border-soft);
      color: var(--text-main);
      font-weight: 600;
      transition: all 0.18s ease;
    }

    .btn-secondary-doc:hover {
      border-color: #F97316;
      color: #EA580C;
    }

    html.dark .btn-secondary-doc:hover {
      color: #FB923C;
    }

    /* Sticky TOC active link */
    .toc-link-active {
      background-color: #FFF7ED;
      color: #EA580C;
      border-left: 3px solid #EA580C;
      font-weight: 600;
    }

    html.dark .toc-link-active {
      background-color: rgba(249, 115, 22, 0.15);
      color: #FB923C;
      border-left: 3px solid #FB923C;
    }
  </style>
</head>
<body class="min-h-screen flex flex-col selection:bg-orange-500 selection:text-white">

  <!-- =====================================================================
       STICKY NOTION TOP BAR (BREADCRUMB + READING MODE + QUICK ACTIONS)
       ===================================================================== -->
  <header class="sticky top-0 z-40 bg-white/95 dark:bg-[#181B20]/95 backdrop-blur-md border-b border-[#E5E0D8] dark:border-slate-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-wrap items-center justify-between py-2.5 gap-3">
        <!-- Notion-Style Page Breadcrumb -->
        <div class="flex items-center gap-2.5 cursor-pointer" id="brandHomeTrigger">
          <img
            src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAoHBwgHBgoICAgLCgoLDhgQDg0NDh0VFhEYIx8lJCIfIiEmKzcvJik0KSEiMEExNDk7Pj4+JS5ESUM8SDc9Pjv/2wBDAQoLCw4NDhwQEBw7KCIoOzs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozs7Ozv/wAARCACqAKoDASIAAhEBAxEB/8QAHAAAAQUBAQEAAAAAAAAAAAAABAECAwUGBwAI/8QAQxAAAgEDAgQEAwQHBgMJAAAAAQIDAAQRBSEGEjFBE1FhcSIygRSRobEHFSMzQtHwQ1JicsHhJILxFhclNFNjkrKz/8QAGQEAAwEBAQAAAAAAAAAAAAAAAQIDBAUA/8QALxEAAgIBAwIDBwQDAQAAAAAAAQIAEQMEEiExUUFhkQUTIjJxgaEUI0LBFbHR8P/aAAwDAQACEQMRAD8At4DUki1DCfiosqCua6imjMD+BgvSlzSsMGkpiOZ4HiFWrb4omRM70DbnDj3qzUBlFTva0bILAMBkioV1watZYxy1XzLg1a7EiOsHp4pMUopJSPViDU6SA9djQ4pRSFbjhvA9IZkMN/vpOTHSoUkI9akWQV4Fh0i7B1Ux3KaURsaUSY704SZo7j2ntr946OAd6KjRVXpUEeWqRn5RQN+MGweMSZwBtQ6rzHfpXmJkalZggwK9CY8yBRgUzxvUVAzk1HzNQ6w8CCxdaOQZShI1o6IfDVK5g6rUEkXBphZVG5xU04xmrfhzSIbqCW7u4ldZDyRhvLuayavUtiIVOSZp0uBcgZ36CUiMFOSQBVnazRyoeR1OOwNBTWP2PWlspBmMTDGe6k/70frEUFhrgMEaxILcsQu2ev8AKuaPaTM1kUBwe9zpH2cgXaCSSCR2qLPJHEmZHVR6mquaWNzlHBq3sLKzisP1vq2ZPEOUQ7gDttUN9d6LdWjhLJ4LgECMBOXP18qJ9o5BytAecRfZ+MmjZ8xUp+dc4yKdzKBnmGDWp1BtG0rwY7jT1YyrsVQHGMDv701NEsotbiKxBoJoWYRsMgHb+dH9ZqCaoH14g/SaerO4enMzHix/3hU6QyPEZURmjHVwNh71f3Nxplu0ivocnLGSDIIRy7d81noM6nqr2tk7RW80nxxKfhUeo9B+dTPtLIjBWo/S46+zseRSy2AO9Rokjx84rwmi/wDUFaDWNLtbFIb6G1SRIGxLH2ZT39wal0ufTtTguH/VUMfgDO4BzsT/AKUw12ffsND1g/R4Nm8WR9pnRNEf7QVMk9vkZlUZoy2vdP1O/tbddMihBkyxyNxg7bUbHp+nz6hqOnCBEkwrRkDoOXt5YO9BfaGZhxX5hbQ4VNNuHp9IE0iQoWYgAd6DkvIn38QYNLp1pLfajDp8qnlgY+KPRe1Xlna6ZcavfBLONkhVV+XILb5x+VH/ACGXIbQADpz+Yp0OLGKeyevFfaUQu7dV2lUmkL8+4OQfKrea+0uGMtJoUsa9OZoQB9+aprVcRkleUMxKr5Cr6bVvky7G5HlJajSomL3iWD51zHqmetP8IVIqk07wzXW5nJ4gSJRUa7VEi0SowteMaBSxNcXMVtH80rAZ8q0l9e6Xp6Q6fMZR4AVwIwdsdM4rNXI5nDAlWHQjqKi+J3LyO0jt1Zjk1ydRp875yR079hOphz4BgUMenh3M0mpxw6ithqtschZVUk7ZHMP9aG1+3ku+IVt4hl2tiB+NVNpaXF5MlpBJJhm5uUHZfWqLjHiCz0wS2Wn6lJc3TAxT3HN+7HdVPc1gfT5S1OvWr+02pqMSgFGuroV3m2sxFregJYCVY7m3IxncZB2PqKBu+G7uBZtSvLlHmGM5cnI8t9h7CuV2XFF5o0MfKOdP4UbIKexG49qt4eNL7UUWW4hKxDdQ0pct9+1TfTORtK3XnKpnQGw1eVes63quq2unyWy3Ft4pkGQ2B8I28/enssh4igl5sxNbMFHluCf9K5NLxDe6jqNvZW7DxFwZi7c4Uf3fuo6/1nUrGQTcytGq8sZ8VgxPl6ADc1TZqCbK/mTC4NvDc/SdHvoNcuVmhQ2qwvkDY55f50BoVimjw3d9eBVMbFMrv06n6n8q5zf8cajp1skk3P4jqGEfjuOvQdevf0qkb9IupvBJCLdFZ25lbxGIB8yp6n1pTiys4fbz5mMGRU93uFHsDO22Go6XetLZQmUm45mZZAdyeuM/lQmhWzWX62tm6x7Z8xg4P3VxfhvW7rS7mTkuPHlkPM0Zc5UjuD5771eR8W6l4kzrCNxlgHYH1ye9F8WYuDtBr7QK2HYQGIB8DzyDNRwvkcVOSdvETG3+A1aatffq/ixp1IDBl2z8wxuPuzWE0m61Ey3F6nKZZAHX4sKcbcoI+UivXPEAv7FJ2DJOrkMxbLRSDpnPUdqmNJlAC+d3NB1GIuXPaqnV76e10+0uNVg/e3SqEPmcbH+ftQHCHP4l4CcuQu5Pfesdw1xJp2pXS2WsSyWrZ5Yjz/swx6ZB6Z+6tLNpdxa3TqJZIH7shIDDsauNPmZg4HTwv8zI2fDjQ4yevjXoJbX9lrt9atbzNaBGOTy5ycVTWKtNHhgAUPKfpTzbT4+LUrn/AOZ/nUkHh2sXhx5Izkk9zWjS48qZt5HHmbmXUZcb4NgPoKhKQqDUnhioo3LGpOeurZM5RQSvjSpJDypUgUKtB3EvYVW4INK2Wpp6dM0mcmrPQ7Rbi8M0gzFbjnbPc/wj7/ypWIUWYQLMreIZrzTtKbRtKkWPUrtA95cvkJZwHPU9idwAN+vvXMJbOytXPgFpuXbx5DjPsOij8a0/H/ESi+l02F+WMsZbqZT8UrHt6DAA9hWLVRfDxBGYUHRwxyfp0rnkljZmvELF+EmkSO7GOZVjHVydsdcDz6U271WNV8C1HMRsH/u0Bc25W4SJp3lZiB8R2GamuIo7ZFggUmSQ4yRv/Ro8S/PQQ7RrmS1tZZUcia4OOcHcDP8AtRd5q0kgtkdi2GKsSd2zufwFVVnJyMkDYBWLBH+LJpmouySwFRsrFj6D+jQuEEy3vrB9c1h18RgQAfh82GfwUCjG4Dg5FxfOr7H5cge1T8Jr4l1eTdeUgA/QY/KtJNNFAA00scQ/9xgv51zs+bIHpZ1cODEcYLDkzCalwy2i8t2lwZFjIYbdd9wfpRl3qcMes2MiDDhf2mB839DIq34gurS50C78O5gcqmRyyAny/wBawNzcPNfrLg4UAKe3QbfdWnT5HZfimXVIiv8ABL+71V47qVhhYrnaQLsMg5BxQVzdGK58Zzlbj5z25/P6io7l0nsmI6EZz5H/AK1Xx3n7AwzqZIyNiOq/7itPWZLljmzvZ1iuJDCzEDxFPQeYPQj0Ndo4ZvG1PQ20uYEalpSiMlnL+IuMqwJ3IYb/AIdq4XpNvDearb2krZimkVCxUgAHbJ8utdH4NGoaffwXjSF0jtfAbm+ZZI5CCjeeBnB8jg9KYCzIOR0M1LTFj1pUYsetE6tAi3S3MP7m5XxFx2PeobdMkVpUAi5mZjcLhBC1N4Z8qWJAACad4opriEXK64mCjANV0jlmp0shYneoqYCeMUCir/WIeHNK0xrg8kd9cSSSOT0VEYqPqQKFxkYFHcW6Tb6q1rp1wuY7VYmHowOfx6VPIC1LGWubnKRo0l1Lcatq5OI1FxNF2DSfuoz6kfEfIACq+C48ScjYLnCjHQYzWr18SXelGwhP/E6hrk/i7fKiFYwT6DKge9YhW8GdXGw5sHPmMjBrJ4zVjbiMeRpLkT4yofJPl2H5VYWFxZNrHjXbSeDHgKVQnfv/AF61HZaZLNFLHKlyA/xQrHFkysPl678u/YGi7a2TToTHf6RBJM7H4rmV0I9MZB+tTNsCKmpCqsDcC1aOGLV2nsJlltpOaSNl/gGdwR2wc0Rp7RXer28MqkxyhkZe+43FWdrZxwSfbzogkhQbvBcMygd+pYem5xvvUF9pdtZTQajpV9A0ORIkMkgWVMdV3+o33pCxA2mUUAnfECaxw5qN1pdmryNLylZkQseXHbsD5k15NFgkPj6xrMEMjfNGCZ5fqdwK22g6WeMre61DUJ5LbTrfOY1GT0zjyG2MsQSc7YxVBbcM3ut3MUGmWtvZRXPO0RuCWd0X5nY9huNgO9FMbEWeIj51Bocyh1Sw0RbdVsbq5lnZwHeRMKq9zjAz9KZLZ2Q0Uol4ZJkfxEDQMpO24z0P+lFWsuo2LyNFdJiBuV0kVSp3wcAjf6VeajcFNLXUpNOisb+2lxJ4SLySrgjPl5H67bUdlVzFXMCTQmCt7rlV42GYzsfLHn6GprOGFn8OQOzOcRsg5s+m3epri2lhu/s08SCaUhi6kqU59/rtW6h4Q0pLC0jtfDlvpiOcMnxJ3OPbIA9TT7hIOdvzTNaTp1lcySRyCT90zRtG3K/Oo5sb7bgEb98VrdOlvmMN1p8F1J9rCvcfaoVijYYGJAwY4fGAcDDe+9UWvPZ2cct/pkjyTQnwppCuPEJ+SQHJJ3BU53IINbfRrV7TR7K3kHxxQIrehAq+MWZkY7hul/ADd6C8Z3a1k5l/yn+jTbaLBFT6GuZpojuJYiMV4YiTHerLwSIDyAYsj8q4FQ59a8TvvTOamqCUvWnBc0qqTUyRZ7VYCJc9bRc00YPQsPzq41ROfVZyRncD8KCgi5XQ+RBq01Nf/EJD54P4VJuHEYcqZkLjhpX1XV7t5fChvbVWSTP7iRW5mbH/ACK30Nc/+0JYazBeSWSu00bTvbgcwQuC3vgDDeYBrqms6VLq9p9mS/e1iJzKqxK4lX+6c9vTv3rJatw9Y6K0WpGWe6kFxi8uJ2yxicFG2GwAyDtWfIpuxKo1S60G+TReArnV4Qhv7xGEZ2Lsc4JJ6nBPfyFU0vDenaUtqdct7m7ub+2klEqEsxmyMZ3+UAn3+6huEohHxDHo1y3I0TSpGCcBgw2z2IyD9/pXQ9WRbjT7ZJYsy2pzBMMYG2OVgcbEDH0BqDMQOJdFsC5zPhS2YakBECIZi8Fxy/I4ZTygr2PWhNF0htVt5ZXupIo435EEe24AydupraajxBa6ZZS5FlBIwJW1tH8RpZSCFyQO2c+dV2g6dLZ6RFbSwOJyBIz52UkklT6/LWPLkYL15M6Wlxgv8Q4EXhTUJtLkv+H7twyvKrlztzZAUH2Pw5960nFulRX+n6Xewgx29rzxTpESvIGAGTjflyN/fyqi1LRXuXivLOaKG8t9gZGwrr3Vv547kU19b14IUl4dEvOPiMNwCrD2BO1MuTct+sXJh2tXnxH2nCFnbtOL7U0uWuFKRhMMwJ/iOTvjufIVH+kBIYdHEEYz9omihiwuOblXBOPuP1oZNc1uyB+x8N2Fkc58STBI+gqq1i81G5lg1DVL1Z7vxOSBFQBIh1JHY4xttjO5zivKwAq+Yow5B8RHAlVq4EHFxeZh4IUICNwgChcnHbrv71q7adke7mV0kZLJmjaPJUZ8qyd6kbxzC0DPygs0mCXY53LH+hRPDF9FHKLad3xcWzWxAyeVt8bDr1H0Bq6JQExalg4JEIsbYSKycufEvLWIL22kz+S10eKPmYnHespw/pkdxq6vBKs1vYszSSoT4ck5HKFXOM8ozk+ZA7VuI4xGMmt2IULmNjuhmlKI7yLzORQsp/auPJjROm/FqMWOgyfwoOV8yuR3Y17+RjfxjWNMzXjXqeLBEjAoqKMGmRpmio1AFULRAJ4Jij9RAcwTj+0iGfcUJRZPiaSdvit2z/ymoNwQZVR1ErbmURxkd6pLlEu0eKZQ8cqlGU9CDsaKupi7YptrD4j5xkCqgRCamO1DRriymsBqVq1zpsFxGjXscmGEJPLh+4wCNxscCirzhO3gv3hle5dImK4a4Y5H/TFa7V7jS7bSpV1eaKO0mQxsJGxzg9gOpPtWRsOKrMcthq80sTIOS0v7lOXxox8vir1Q425u+N8Vy9ZjYcoZ09DlQN+4IbY6Pp9gOe1tIo5MY52BJH1NDQcQ2MWozwXd09i9uxQyXETyBsdeVE2H1NXBDIFY45G3RgQysPMEbEUDeaTZ3V1HeNGouYiMMRzK2OgYd8dj1rlJkAb9ydpl3L8HEllv7IxCax+33bvuGSzjt0PrlgW/CgtCn1CbUL6S9kyi4REIHwP1IGw6DGfejPtqXErWqPMsqj4ysRXA9CfwqSNYreLCKIo065PTuST386pkzAjaojLhVeQb85HeSwW680z8vMcKoGWc+Sgbk1jNce4nvY5XVYQgISHmyyZ7tjYE+W9RalxAkesXk3ikBnCjrzCMDYKewJBqmuuJbu5t/sVspSEvzdAXbt19q04MOymM52q1ORhsHSGXGuPZwSQ2xCtylZCO42+bz36Ci+Fka+RoOZb1S+9ml19nkfvseXfPlkVmhptzISXAiDfwk71d8PWQg1a2VC6M0qqXB+I5I2HlWscdJz8zFgWM69oVxYz6Yn2CA26QkxNbsnK0LDqpHn+dWBas9w5e28+oa8qSr4p1KRjF0YIAFBx5HHWrtnrYjWJjqWOmNySTz9BDET9TVdnNHf8AltF8nunyP8ooECgvNmFuBUdS4pVWpOWqRJAhzRCjaoYlogbCiYRPHYZplrqCW96qyH9jJ8EnsagupwoIFVcjF2Od6UrYqG65k99ZSWl+9u3RTlT5r2qHVb2XSdNja1hWa7uZkt4EfZfEY7c3oBk1Z3AvtU4fdLARfra3TFu03Rl9fPAz9QK5Zq2rrDcyP+tdT1GazuFeEysEjVozuSuOp3wO3rU2ylRt8YdtmxDuJbr9TyiTxRqepup8W/l3EZzgJEvRBkH1rDzu/wBnF9cZma4Zscx642JY9SautRv0vxNJG3NHIzsuewY5H4mq6zX7RpsSuo5lBjIbowzt+OazEmXxpQF+MM0Sy4ugt/H03nit5t/CdlCOPPkb860trecVxpy3OmW8m2MrMoI+81oeGuKtPgtEthb28szAL4cnzKVUZA23FbHVdRttN0+2uzYW5Ey8zBgAFGM+VclshcktQryM7aJ7sgJZvznL5L3iFbcxx6QXA6886HOfrVXd2XF2qsI7kpbQ91SRc/nXWrY22paHqV59lhjYgleUdMKOlG39zp+kW1sX05JPFUY5UXI2HnSqTt3igO9GOzW20g32sTg9zol23LposZYgzB+nNJKR3z0AotOFb+2g/Z2qr5rG4Z/qf5V2W60ewOqWMiReHFcZLRdMnGRt29qk1WeGBZrefRWMKD9nIijB+75at73Ko5oAf++0gUxORwST9BX/AGcIdUt1IZOVh2xk5oJb2WN+aP8AZsDs2dwfP3q14uleTX5LeCAqwVclhgN6+tVsWjuwLzvJkDOQRt9K3Yn3oG7zDlQY3K9ppNO1NpeH2ulULqOj8jQXCn45UaQBkf8AvA81dPtIGvLtYV7n4vQd64zplqmXSea8VJCoUwuAxwQR8PQnIBFdm020l0DSjHLf3d1d3gDE3RUvAmPl2H9Gr4zVgTCVAMI1C4W4uyI/3UQ5Ex0wO9QouaZGmaKRMCtSihUmTcVVxTtqU02vQSONMCmzyhFqViEUmqu7mJOAaI5hEgml52OK9BEXcVGoJO9WVpFhc04imE2/NCQ0Z5WXoaz/ABpwb+vIZdX0eFRfqC1xaqMeP5sv+L8/etGFpF8SW9S3imaECNpHdB8eB2HrWXUEKu4zRgUs22fO4eW1ZlkVkCsQQQQUOdwRREErQ5aMZVt8dR9K69xXwNFrii5tyz3Mycyuy4kIA/jH8Q9evvXJtR0DV9CYpcWrqgbAcKSh9D5H3rGmZW4PBm5sTAWORLThuRZeILdgcHB2P+Ugj7j+Fdc4tYHhe0wQf2Lf/nXEpY9W0X7PeT2L2y8waOVt8H+uxrRw8QTa3pckE1zFZyZ5eViQHU9g24B7EHFZM+N8jEp0I/uasOVcKjfwQb9ROm6ER/2QvskfKf8A6irTVtbj0iztneFJA0eSWOAoAG9cbh4nubC1+zmZJQg5ckZO3bIODVPrPG2oX0bWiLGsTDDFcksPLPlmppjzAbBx5wtkwMd5N+NVOtWuswcUarGXvEjijYqpiPyt1G57nzrU2cd7ZmVtRvYprRV+FnHxD3PtXzto1zeadP8Aao5XVmGGU7hh6itKOK9WvV8CC25223BZguehx0FeOJ8TFhzfjf8AuH3iZlC9PKr9JLxXJbtqilFwMHBx0BOw+6qdwZHjgUFvEOeVereg+uKtbjhbXmuYVuvAZrsc5leTlVB5sT29q13CvCEdg8dwzSvOYmYXAxzFQccsY/h3PU7+1VxZUx4woNmQzYmyZC7cCLwxwtHoKR6rq0Qa/IzbWp/sv8Tev5VblnnlaWRizuck+dJdxeDegK8skUq5R5Tk5HUZ74qeGPOK6mmKst+M5uoVkIB6GOij6USVwMUqJyilIrTM0iIpMVIRSYr0MDun5UwKqHPM1WF6xoDG9OBwIt3JIEy4q2hTAFV9qvxCrVcKgpCY9TxwKgmj52WRJGilT5JFO4p7NUZakdFdabpGR2RrU8yOfUb9EmMjcssvKn2lOkad9vfeimgsdWmuJij3iqUh5VbAOB858+tDdfKoJFAlEkTPFIOjI2D/AL1zsmhI5U2OxnRx6sH5hR7iP4i4TtuIbdLKWUxWcDCKMAElnHXOO2awdz+ia/t45ZrW+IjQv8MgBwF+uT0rewXN5BE0Q5J0Llx4rFWDHqcj1oe5ea5itYpo3CW4w/K+S+TuRWR1y4/lUgzVjbHkPLAj8/1ObQ/o4165L/FBMqDP7FiwPpkD8K9/3Y63yG4ZIkQ8uCAcbkeldTt7y3hszbYvoFWUvE8XzOD2bFMe6nmeyaDxv+FjHOj5AZgfxOKHvcx+vaowTEOKFd7mHX9F2pi4gW4uSqysBhE7+ROdtq2nD3Cmn8PIEkuFuI7stFzfN8fv22zRd1qUjOr2kU8MniiQ+IFCdNwcdaHu7y4u4VgaOC3iV+cCIb83nn3ptmR+gJib1TkkLCXaGytp5I7PDWz8jR3B5jJETjYmh57oTSWosFmtRbow36qSc49agZDNIJZ3eZxsGkbOKJiT0rTi0LdW4HaZsmtA+Tk945I5JpvGuJmmlxjmboPYdqPhi6UyCL0osAItdFUTGKQVOc7tkNtEIAFMOKVmqMmiItRTSYrwNLRuCVN4KBHWj7vpQI61b+IiLDLRdxR0jYGKEs/mFTy/MakJUxpNNpT0ppposa7dhTVXO5pDT/4K95z08TnYUqpSDtUy0RPGIqelPcci09aimrxEAg7nJpmM049a8OtLDHImTRkMfpUEXWjoOooGCTxqFXpSO1Ob5ahbrSxohNNpTSUZ6KKdTRTqEM//2Q=="
            alt="ander.creative profile badge"
            class="w-9 h-9 rounded-full object-cover border-2 border-orange-500 shadow-sm"
          />
          <div class="flex items-center gap-1.5 text-sm">
            <span class="font-display font-bold text-slate-900 dark:text-white">ander.creative</span>
            <span class="text-slate-400">/</span>
            <span class="font-medium text-slate-700 dark:text-slate-200 truncate max-w-[180px] sm:max-w-none">AI Creative &amp; Marketing Toolkit</span>
            <span class="hidden md:inline-flex items-center px-2 py-0.5 rounded-full text-[11px] font-semibold bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300 border border-orange-200 dark:border-orange-800">
              AI Creative Tips
            </span>
          </div>
        </div>

        <!-- Right Controls: Doc Mode Toggle, Workflow Progress, My Stack, Theme & Notion Guide -->
        <div class="flex items-center gap-2">
          <!-- View Mode Toggle: Full Notion Doc vs Single Section Focus -->
          <div class="hidden sm:flex items-center bg-[#F3F1EC] dark:bg-slate-800 p-0.5 rounded-lg border border-[#E5E0D8] dark:border-slate-700 text-xs">
            <button type="button" id="btnModeFullDoc" class="px-2.5 py-1 rounded-md font-semibold bg-white dark:bg-slate-900 text-orange-700 dark:text-orange-400 shadow-sm transition">
              📄 Full Notion Doc
            </button>
            <button type="button" id="btnModeTabbed" class="px-2.5 py-1 rounded-md font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition">
              🗂️ Focus Tab View
            </button>
          </div>

          <div class="hidden lg:flex items-center gap-1.5 bg-[#F3F1EC] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 px-2.5 py-1 rounded-lg text-xs">
            <span class="w-2 h-2 rounded-full bg-emerald-600"></span>
            <span class="text-slate-600 dark:text-slate-300">Checklist:</span>
            <span id="headerWorkflowProgress" class="font-bold text-emerald-700 dark:text-emerald-400">2/6 Steps</span>
          </div>

          <button
            id="btnSavedStack"
            type="button"
            class="btn-secondary-doc px-3 py-1.5 rounded-lg text-xs flex items-center gap-1.5"
          >
            <span>★ My Stack</span>
            <span id="savedStackCount" class="bg-orange-600 text-white px-1.5 py-0.2 rounded-full text-[11px] font-bold">3</span>
          </button>

          <button
            id="btnToggleTheme"
            type="button"
            aria-label="Toggle Light or Dark Reading Mode"
            class="btn-secondary-doc px-2.5 py-1.5 rounded-lg text-xs"
            title="Switch between Warm Paper and Dark Slate"
          >
            ☀️ / 🌙
          </button>

          <button
            id="btnNotionCodeModal"
            type="button"
            class="btn-primary-orange px-3 py-1.5 rounded-lg text-xs flex items-center gap-1.5"
          >
            <span>⚡ Notion Embed Guide</span>
          </button>
        </div>
      </div>

      <!-- Horizontal Quick-Jump Bar (Works for both scrolling in Full Doc Mode & switching in Tab Mode) -->
      <nav aria-label="Toolkit Navigation" class="flex items-center gap-1.5 overflow-x-auto py-2 border-t border-[#E5E0D8]/70 dark:border-slate-800">
        <button data-tab="start-here" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-semibold transition-all flex items-center gap-1.5 bg-orange-600 text-white">
          <span>🏠</span><span>Start Here</span>
        </button>
        <button data-tab="core-ai-tools" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span class="font-mono text-orange-600 font-bold text-xs">01</span><span>Core AI Tools</span>
        </button>
        <button data-tab="prompt-library" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span class="font-mono text-orange-600 font-bold text-xs">02</span><span>Prompt Library</span>
        </button>
        <button data-tab="canva-templates" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span class="font-mono text-orange-600 font-bold text-xs">03</span><span>Canva Template Library</span>
        </button>
        <button data-tab="capcut-templates" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span class="font-mono text-orange-600 font-bold text-xs">04</span><span>CapCut Template Library</span>
        </button>
        <button data-tab="workflows" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span>⚙️</span><span>Content Creation Workflows</span>
        </button>
        <button data-tab="seo-aeo" class="nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800">
          <span>📈</span><span>SEO &amp; AEO Playbook for Creators</span>
        </button>
      </nav>
    </div>
  </header>

  <!-- =====================================================================
       NOTION DOCUMENT COVER BANNER & AUTHOR PROFILE HEADER
       ===================================================================== -->
  <div class="notion-cover-banner">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 sm:py-8">
      <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-6">
        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-5">
          <!-- Updated TikTok Profile Picture Badge -->
          <div class="relative shrink-0">
            <img
              src="data:image/jpeg;base64,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"
              alt="AI Creative Tips — ander.creative profile picture"
              class="w-24 h-24 sm:w-28 sm:h-28 rounded-2xl object-cover border-4 border-white shadow-lg"
            />
            <span class="absolute -bottom-2 -right-2 bg-orange-600 text-white text-[11px] font-bold px-2.5 py-0.5 rounded-full shadow">
              @ander.creative
            </span>
          </div>
          <div>
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/90 dark:bg-slate-900/90 border border-orange-300 text-orange-700 dark:text-orange-400 text-xs font-bold mb-2 shadow-sm">
              <span>✨ Practical Creator Resource Hub</span>
              <span>•</span>
              <span>Updated 2026 Edition</span>
            </div>
            <h1 class="font-display text-2xl sm:text-4xl font-extrabold text-slate-900 dark:text-white tracking-tight">
              AI Creative &amp; Marketing Toolkit
            </h1>
            <p class="text-slate-700 dark:text-slate-200 text-sm sm:text-base mt-1 max-w-2xl">
              Your step-by-step Notion resource doc to find the right AI tools, copy-paste tested prompts, customize Canva &amp; CapCut templates, and structure content for search &amp; answer engines.
            </p>
          </div>
        </div>

        <!-- Character Mood / Guide Strip -->
        <div class="bg-white/90 dark:bg-slate-900/90 backdrop-blur border border-white/80 dark:border-slate-700 rounded-2xl p-3 shadow-sm flex items-center gap-3 shrink-0">
          <img
            src="data:image/jpeg;base64,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"
            alt="Welcome character reaction"
            class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
          />
          <div class="text-xs">
            <span class="font-bold text-orange-600 dark:text-orange-400 uppercase tracking-wider block">Your Guide: Ander</span>
            <p class="text-slate-700 dark:text-slate-300 max-w-[190px] leading-snug mt-0.5">
              Look for my character callouts across each section for quick shortcuts &amp; honest tips!
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- =====================================================================
       MAIN NOTION DOCUMENT LAYOUT (STICKY SIDEBAR TOC + READABLE DOC BODY)
       ===================================================================== -->
  <div class="max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8 flex-1">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-start">

      <!-- FULL-WIDTH NOTION DOCUMENT CONTENT FLOW (TOP NAV ONLY) -->
      <main class="lg:col-span-12 space-y-10">

        <!-- =================================================================
             VIEW 1: START HERE (OVERVIEW, 01-04 CARDS, 6-STEP WORKFLOW)
             ================================================================= -->
        <div id="view-start-here" class="tab-view space-y-10">

          <!-- SECTION: START HERE + AEO DIRECT ANSWER BLOCK -->
          <section class="doc-card p-6 sm:p-8 space-y-6">
            <!-- Top Quick Page Directory Links (Exact 6 Links from User Request) -->
            <div class="pb-5 border-b border-[#E5E0D8] dark:border-slate-700">
              <p class="text-xs font-bold uppercase tracking-wider text-slate-500 dark:text-slate-400 mb-3">
                📂 Notion Sub-Pages &amp; Resource Libraries (Click any page to jump directly)
              </p>
              <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-2.5">
                <button type="button" data-goto="core-ai-tools" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>⚡ Core AI Tools</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
                <button type="button" data-goto="workflows" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>⚙️ Content Creation Workflows</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
                <button type="button" data-goto="seo-aeo" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>📈 SEO &amp; AEO Playbook</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
                <button type="button" data-goto="prompt-library" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>💬 Prompt Library</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
                <button type="button" data-goto="canva-templates" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>🎨 Canva Template Library</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
                <button type="button" data-goto="capcut-templates" class="quick-nav-pill text-left px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 text-xs sm:text-sm font-semibold flex items-center justify-between group transition">
                  <span>🎬 CapCut Template Library</span>
                  <span class="text-orange-600 group-hover:translate-x-0.5 transition-transform">→</span>
                </button>
              </div>
            </div>

            <!-- Start Here Main Intro + Welcome Character -->
            <div class="grid grid-cols-1 md:grid-cols-12 gap-6 items-center">
              <div class="md:col-span-8 space-y-3">
                <div class="inline-flex items-center gap-2 text-xs font-bold uppercase tracking-wider text-orange-600 dark:text-orange-400">
                  <span>👋 Start Here</span>
                </div>
                <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">
                  Welcome to your practical resource hub for AI-powered content creation and marketing.
                </h2>
                <p class="text-slate-700 dark:text-slate-300 text-base leading-relaxed">
                  Whether you're building a brand, growing a business, or creating content for clients, this toolkit helps you find the right tools, develop stronger ideas, and turn those ideas into publishable content.
                </p>
              </div>
              <div class="md:col-span-4 flex justify-center">
                <div class="char-sticker-frame w-48 sm:w-52">
                  <img
                    src="data:image/jpeg;base64,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"
                    alt="Ander Creative Welcome Reaction"
                    class="w-full h-36 object-cover"
                  />
                  <div class="bg-[#1E242B] px-3 py-1.5 text-center border-t border-slate-700">
                    <span class="text-[11px] font-mono font-semibold text-emerald-400">✓ USER CONNECTED • WELCOME!</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Before vs After Character Callout: Frustrated Blank Page vs Insight Goal -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="p-4 rounded-xl bg-rose-50/70 dark:bg-rose-950/20 border border-rose-200 dark:border-rose-900/60 flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Frustrated staring at a blank page"
                  class="w-16 h-16 rounded-xl object-cover shrink-0 border-2 border-white shadow"
                />
                <div>
                  <span class="text-[11px] font-bold uppercase tracking-wider text-rose-700 dark:text-rose-400 block">The Old Way (Frustrated)</span>
                  <p class="text-xs sm:text-sm text-slate-700 dark:text-slate-300 mt-0.5">
                    Collecting dozens of disconnected AI tools, guessing how to prompt, and spending hours staring at a blank page.
                  </p>
                </div>
              </div>

              <div class="notion-callout-warm p-4 flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Insightful repeatable system"
                  class="w-16 h-16 rounded-xl object-cover shrink-0 border-2 border-white shadow"
                />
                <div>
                  <span class="text-[11px] font-bold uppercase tracking-wider text-orange-700 dark:text-orange-400 block">The Toolkit Goal</span>
                  <p class="text-xs sm:text-sm font-semibold text-slate-900 dark:text-white mt-0.5">
                    The goal: spend less time staring at a blank page and more time creating content that serves your audience.
                  </p>
                </div>
              </div>
            </div>

            <!-- Character Callouts Strip -->
            <div class="pt-2 border-t border-[#E5E0D8] dark:border-slate-700">
              <div class="flex items-center justify-between mb-2.5">
                <span class="text-xs font-bold uppercase tracking-wider text-slate-500 dark:text-slate-400">🎭 Character Callouts &amp; Shortcuts</span>
                <span class="text-[11px] text-emerald-700 dark:text-emerald-400 font-semibold">Click any character to open</span>
              </div>
              <div class="grid grid-cols-2 sm:grid-cols-4 gap-2.5">
                <button type="button" data-goto="core-ai-tools" class="p-2.5 rounded-xl bg-[#F3F1EC] dark:bg-slate-800 hover:border-orange-500 border border-transparent text-left flex items-center gap-2.5 transition">
                  <img src="data:image/jpeg;base64,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" alt="Skeptical reaction" class="w-10 h-10 rounded-lg object-cover shrink-0" />
                  <div class="min-w-0">
                    <p class="text-xs font-bold truncate">Unsure?</p>
                    <p class="text-[11px] text-slate-500 dark:text-slate-400 truncate">Pick a Tool</p>
                  </div>
                </button>
                <button type="button" data-goto="prompt-library" class="p-2.5 rounded-xl bg-[#F3F1EC] dark:bg-slate-800 hover:border-orange-500 border border-transparent text-left flex items-center gap-2.5 transition">
                  <img src="data:image/jpeg;base64,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" alt="Insight reaction" class="w-10 h-10 rounded-lg object-cover shrink-0" />
                  <div class="min-w-0">
                    <p class="text-xs font-bold truncate">Need Ideas?</p>
                    <p class="text-[11px] text-slate-500 dark:text-slate-400 truncate">Use Prompts</p>
                  </div>
                </button>
                <button type="button" data-goto="workflows" class="p-2.5 rounded-xl bg-[#F3F1EC] dark:bg-slate-800 hover:border-orange-500 border border-transparent text-left flex items-center gap-2.5 transition">
                  <img src="data:image/jpeg;base64,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" alt="Teaching workflow reaction" class="w-10 h-10 rounded-lg object-cover shrink-0" />
                  <div class="min-w-0">
                    <p class="text-xs font-bold truncate">Step-by-Step</p>
                    <p class="text-[11px] text-slate-500 dark:text-slate-400 truncate">Workflows</p>
                  </div>
                </button>
                <button type="button" data-goto="seo-aeo" class="p-2.5 rounded-xl bg-[#F3F1EC] dark:bg-slate-800 hover:border-orange-500 border border-transparent text-left flex items-center gap-2.5 transition">
                  <img src="data:image/jpeg;base64,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" alt="Deep audit reaction" class="w-10 h-10 rounded-lg object-cover shrink-0" />
                  <div class="min-w-0">
                    <p class="text-xs font-bold truncate">Get Found</p>
                    <p class="text-[11px] text-slate-500 dark:text-slate-400 truncate">SEO &amp; AEO</p>
                  </div>
                </button>
              </div>
            </div>

            <!-- Quick Action Buttons -->
            <div class="flex flex-wrap items-center gap-3">
              <a href="#section-explore-toolkit" class="btn-primary-orange px-4 py-2 rounded-xl text-xs sm:text-sm inline-flex items-center gap-2">
                <span>Explore the Toolkit</span><span>↓</span>
              </a>
              <button type="button" data-goto="workflows" class="quick-nav-pill btn-secondary-doc px-4 py-2 rounded-xl text-xs sm:text-sm inline-flex items-center gap-2">
                <span>Launch Workflow Studio</span>
                <span>→</span>
              </button>
              <button type="button" data-goto="prompt-library" class="quick-nav-pill btn-secondary-doc px-4 py-2 rounded-xl text-xs sm:text-sm">
                Copy-Paste Prompts
              </button>
            </div>

            <!-- Interactive Creator Velocity & Time-Saved Chart (Clean Editorial Styling) -->
            <div class="bg-[#FAF8F5] dark:bg-slate-900/80 border border-[#E5E0D8] dark:border-slate-700 rounded-2xl p-5">
              <div class="flex flex-wrap items-center justify-between gap-3 mb-4">
                <div>
                  <span class="text-xs font-bold uppercase tracking-wider text-orange-600 dark:text-orange-400 block">📊 Creator Workflow Impact</span>
                  <h3 id="heroChartTitle" class="font-display font-bold text-base sm:text-lg text-slate-900 dark:text-white">
                    Weekly Publishable Assets (Manual vs. Toolkit System)
                  </h3>
                </div>
                <div class="flex items-center gap-1.5 bg-white dark:bg-slate-800 p-1 rounded-xl border border-[#E5E0D8] dark:border-slate-700">
                  <button type="button" id="btnHeroChartOutput" class="px-3 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white transition">
                    Output Growth
                  </button>
                  <button type="button" id="btnHeroChartTime" class="px-3 py-1.5 rounded-lg text-xs font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition">
                    Hours Saved
                  </button>
                </div>
              </div>
              <div class="relative h-56 w-full">
                <canvas id="heroVelocityChart"></canvas>
              </div>
            </div>
          </section>

          <!-- ===============================================================
               SECTION: EXPLORE THE TOOLKIT (01 - 04 WITH CHARACTER REACTIONS)
               =============================================================== -->
          <section id="section-explore-toolkit" class="space-y-5">
            <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-2">
              <div>
                <span class="text-xs font-bold uppercase tracking-wider text-orange-600 dark:text-orange-400">4 Core Resource Pillars</span>
                <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">Explore the Toolkit</h2>
              </div>
              <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-400">
                Choose the starting point that matches where you are stuck right now:
              </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <!-- 01 — Core AI Tools (Paired with SKEPTICAL character reaction) -->
              <article class="doc-card p-6 flex flex-col justify-between">
                <div>
                  <div class="flex items-start justify-between gap-4 mb-4">
                    <div>
                      <span class="inline-block font-mono text-xs font-bold px-2.5 py-1 rounded-md bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300 mb-2">
                        01 — Core AI Tools
                      </span>
                      <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white">01 — Core AI Tools</h3>
                    </div>
                    <img
                      src="data:image/jpeg;base64,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"
                      alt="Skeptical — Not sure which tool to use"
                      class="w-16 h-16 rounded-xl object-cover border-2 border-slate-800 shrink-0 shadow-sm"
                    />
                  </div>
                  <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed mb-4">
                    Discover AI tools for research, writing, design, video, and marketing. Compare what each tool does, what it's best for, and where to get started.
                  </p>
                  <div class="notion-callout-warm p-3.5 mb-5">
                    <p class="text-xs sm:text-sm">
                      <strong class="text-orange-700 dark:text-orange-400 uppercase font-bold mr-1">Start here if:</strong>
                      You're not sure which tool to use.
                    </p>
                  </div>
                </div>
                <button type="button" data-goto="core-ai-tools" class="quick-nav-pill w-full btn-primary-orange py-2.5 px-4 rounded-xl text-sm flex items-center justify-between group">
                  <span>→ Open the Core AI Tools directory</span>
                  <span class="font-mono text-xs opacity-90 group-hover:translate-x-1 transition-transform">OPEN MODULE</span>
                </button>
              </article>

              <!-- 02 — Copy-Paste AI Prompts (Paired with INSIGHT character reaction) -->
              <article class="doc-card p-6 flex flex-col justify-between">
                <div>
                  <div class="flex items-start justify-between gap-4 mb-4">
                    <div>
                      <span class="inline-block font-mono text-xs font-bold px-2.5 py-1 rounded-md bg-blue-100 text-blue-800 dark:bg-blue-950 dark:text-blue-300 mb-2">
                        02 — Copy-Paste AI Prompts
                      </span>
                      <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white">02 — Copy-Paste AI Prompts</h3>
                    </div>
                    <img
                      src="data:image/jpeg;base64,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"
                      alt="Insight — Know what to create, need the prompt"
                      class="w-16 h-16 rounded-xl object-cover border-2 border-slate-800 shrink-0 shadow-sm"
                    />
                  </div>
                  <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed mb-4">
                    Use practical prompts to brainstorm ideas, write social media posts, develop video scripts, improve marketing copy, and repurpose content.
                  </p>
                  <div class="notion-callout-blue p-3.5 mb-5">
                    <p class="text-xs sm:text-sm">
                      <strong class="text-blue-700 dark:text-blue-400 uppercase font-bold mr-1">Start here if:</strong>
                      You know what you need to create but aren't sure how to prompt AI.
                    </p>
                  </div>
                </div>
                <button type="button" data-goto="prompt-library" class="quick-nav-pill w-full btn-primary-orange py-2.5 px-4 rounded-xl text-sm flex items-center justify-between group">
                  <span>→ Explore the Prompt Library</span>
                  <span class="font-mono text-xs opacity-90 group-hover:translate-x-1 transition-transform">OPEN MODULE</span>
                </button>
              </article>

              <!-- 03 — Canva Template Library (Paired with MIND-BLOWN character reaction) -->
              <article class="doc-card p-6 flex flex-col justify-between">
                <div>
                  <div class="flex items-start justify-between gap-4 mb-4">
                    <div>
                      <span class="inline-block font-mono text-xs font-bold px-2.5 py-1 rounded-md bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300 mb-2">
                        03 — Canva Template Library
                      </span>
                      <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white">03 — Canva Template Library</h3>
                    </div>
                    <img
                      src="data:image/jpeg;base64,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"
                      alt="Mind-blown — Polished visuals without designing from scratch"
                      class="w-16 h-16 rounded-xl object-cover border-2 border-slate-800 shrink-0 shadow-sm"
                    />
                  </div>
                  <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed mb-4">
                    Find customizable starting points for social media graphics, educational carousels, content calendars, lead magnets, and other marketing assets.
                  </p>
                  <div class="notion-callout-sage p-3.5 mb-5">
                    <p class="text-xs sm:text-sm">
                      <strong class="text-emerald-700 dark:text-emerald-400 uppercase font-bold mr-1">Start here if:</strong>
                      You want to create polished visuals without designing everything from scratch.
                    </p>
                  </div>
                </div>
                <button type="button" data-goto="canva-templates" class="quick-nav-pill w-full btn-primary-orange py-2.5 px-4 rounded-xl text-sm flex items-center justify-between group">
                  <span>→ Browse Canva Templates</span>
                  <span class="font-mono text-xs opacity-90 group-hover:translate-x-1 transition-transform">OPEN MODULE</span>
                </button>
              </article>

              <!-- 04 — CapCut Template Library (Paired with SUCCESS character reaction) -->
              <article class="doc-card p-6 flex flex-col justify-between">
                <div>
                  <div class="flex items-start justify-between gap-4 mb-4">
                    <div>
                      <span class="inline-block font-mono text-xs font-bold px-2.5 py-1 rounded-md bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300 mb-2">
                        04 — CapCut Template Library
                      </span>
                      <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white">04 — CapCut Template Library</h3>
                    </div>
                    <img
                      src="data:image/jpeg;base64,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"
                      alt="Success — Create videos faster and more consistently"
                      class="w-16 h-16 rounded-xl object-cover border-2 border-slate-800 shrink-0 shadow-sm"
                    />
                  </div>
                  <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed mb-4">
                    Explore repeatable short-form video formats, editing recipes, caption styles, and production ideas for TikTok, Instagram Reels, and other vertical video platforms.
                  </p>
                  <div class="notion-callout-warm p-3.5 mb-5">
                    <p class="text-xs sm:text-sm">
                      <strong class="text-orange-700 dark:text-orange-400 uppercase font-bold mr-1">Start here if:</strong>
                      You want to create videos faster and more consistently.
                    </p>
                  </div>
                </div>
                <button type="button" data-goto="capcut-templates" class="quick-nav-pill w-full btn-primary-orange py-2.5 px-4 rounded-xl text-sm flex items-center justify-between group">
                  <span>→ Explore CapCut Templates</span>
                  <span class="font-mono text-xs opacity-90 group-hover:translate-x-1 transition-transform">OPEN MODULE</span>
                </button>
              </article>
            </div>
          </section>

          <!-- ===============================================================
               SECTION: THE CONTENT CREATION WORKFLOW (STEPS 01-06 + TEACHING CHARACTER)
               =============================================================== -->
          <section id="section-workflow-6" class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-5">
              <div class="flex items-start sm:items-center gap-4">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Teaching the 6-Step Content Creation Workflow"
                  class="w-20 h-16 sm:w-24 sm:h-20 rounded-xl object-cover border-2 border-slate-800 shrink-0 shadow"
                />
                <div>
                  <span class="text-xs font-bold uppercase tracking-wider text-orange-600 dark:text-orange-400">Repeatable 6-Step System</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">The Content Creation Workflow</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm sm:text-base mt-0.5">
                    Use this simple process to turn an idea into a finished piece of content.
                  </p>
                </div>
              </div>
              <button type="button" id="btnResetWorkflowSteps" class="btn-secondary-doc px-3 py-1.5 rounded-lg text-xs self-start md:self-auto shrink-0">
                Reset Tracker
              </button>
            </div>

            <!-- 6-Step Interactive Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4" id="workflowStepsGrid">
              <!-- Step 01 -->
              <div data-step="1" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border-2 border-emerald-600 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300">Step 01</span>
                  <input type="checkbox" checked aria-label="Mark Step 1 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="1" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">1. Research</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Identify a real question, problem, or need your audience has.
                </p>
              </div>

              <!-- Step 02 -->
              <div data-step="2" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border-2 border-emerald-600 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300">Step 02</span>
                  <input type="checkbox" checked aria-label="Mark Step 2 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="2" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">02. Create</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Use an AI prompt to develop the idea, outline, script, or first draft.
                </p>
              </div>

              <!-- Step 03 -->
              <div data-step="3" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300">Step 03</span>
                  <input type="checkbox" aria-label="Mark Step 3 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="3" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">03. Design</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Choose a Canva template or establish the visual direction.
                </p>
              </div>

              <!-- Step 04 -->
              <div data-step="4" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300">Step 04</span>
                  <input type="checkbox" aria-label="Mark Step 4 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="4" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">04. Produce</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Edit your video or finalize your creative asset.
                </p>
              </div>

              <!-- Step 05 -->
              <div data-step="5" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-blue-100 text-blue-800 dark:bg-blue-950 dark:text-blue-300">Step 05</span>
                  <input type="checkbox" aria-label="Mark Step 5 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="5" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">05. Publish</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Adapt the content to the platform and give your audience a clear next step.
                </p>
              </div>

              <!-- Step 06 -->
              <div data-step="6" class="workflow-step-card cursor-pointer rounded-xl p-4 bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition-all">
                <div class="flex items-center justify-between mb-2">
                  <span class="font-mono text-xs font-bold px-2.5 py-0.5 rounded bg-blue-100 text-blue-800 dark:bg-blue-950 dark:text-blue-300">Step 06</span>
                  <input type="checkbox" aria-label="Mark Step 6 Complete" class="step-checkbox w-4 h-4 accent-emerald-600 rounded cursor-pointer" data-step-check="6" />
                </div>
                <p class="text-base font-bold text-slate-900 dark:text-white mb-1">06. Improve</p>
                <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300">
                  — Review performance, learn from feedback, and refine the next version.
                </p>
              </div>
            </div>

            <!-- Dynamic Step Action Bar -->
            <div id="workflowStepInspector" class="notion-callout-sage p-4 flex flex-col sm:flex-row sm:items-center justify-between gap-4">
              <div>
                <span id="inspectorStepBadge" class="text-xs font-mono font-bold uppercase text-emerald-800 dark:text-emerald-300">ACTIVE STAGE: 01. RESEARCH</span>
                <p id="inspectorStepRecommendation" class="text-sm text-slate-800 dark:text-slate-200 mt-0.5">
                  Recommended Toolkit Action: Use Perplexity / AnswerThePublic in Core AI Tools to isolate 3 high-intent audience questions before drafting.
                </p>
              </div>
              <button type="button" id="inspectorStepBtn" data-goto="core-ai-tools" class="quick-nav-pill shrink-0 btn-primary-orange px-4 py-2 rounded-xl text-xs">
                Open Matching Tool →
              </button>
            </div>

            <!-- Philosophy Quote Callout -->
            <blockquote class="notion-callout-warm p-4 sm:p-5">
              <p class="text-sm sm:text-base font-semibold text-slate-900 dark:text-white italic">
                "The objective isn't to automate your creativity. It's to build a process that makes good work easier to repeat."
              </p>
            </blockquote>
          </section>

          <!-- ===============================================================
               FEATURED WORKFLOWS & LEARN SEO & AEO SUMMARY CARDS
               =============================================================== -->
          <section class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <!-- Featured Workflows Summary -->
            <div class="doc-card p-6 flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between gap-3 mb-3">
                  <div>
                    <span class="text-xs font-bold uppercase tracking-wider text-orange-600 dark:text-orange-400">Complete Blueprints</span>
                    <h2 class="font-display text-xl sm:text-2xl font-bold text-slate-900 dark:text-white">Featured Workflows</h2>
                  </div>
                  <img
                    src="data:image/jpeg;base64,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"
                    alt="Workflow Blueprints"
                    class="w-16 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                  />
                </div>
                <p class="text-slate-600 dark:text-slate-300 text-sm mb-4">
                  Start with a complete process instead of collecting disconnected tools.
                </p>
                <div class="space-y-3 mb-5">
                  <div data-workflow-select="short-form" class="workflow-preview-item cursor-pointer p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">🎬 Idea to Short-Form Video</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Turn one audience question into a hook, script, shot list, and edited video.
                    </p>
                  </div>
                  <div data-workflow-select="multi-asset" class="workflow-preview-item cursor-pointer p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">♻️ One Idea, Multiple Assets</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Repurpose one useful topic into a carousel, video, caption, and email.
                    </p>
                  </div>
                  <div data-workflow-select="searchable-article" class="workflow-preview-item cursor-pointer p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 transition">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">🔎 Question to Searchable Article</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Develop a content brief, create a draft, verify claims, and optimize the final article.
                    </p>
                  </div>
                </div>
              </div>
              <button type="button" data-goto="workflows" class="quick-nav-pill w-full btn-secondary-doc py-2.5 px-4 rounded-xl text-sm flex items-center justify-between">
                <span>→ Explore Content Creation Workflows</span>
                <span class="font-mono text-xs">LAUNCH STUDIO</span>
              </button>
            </div>

            <!-- Learn SEO & AEO Summary -->
            <div class="doc-card p-6 flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between gap-3 mb-3">
                  <div>
                    <span class="text-xs font-bold uppercase tracking-wider text-emerald-700 dark:text-emerald-400">Search &amp; AI Visibility</span>
                    <h2 class="font-display text-xl sm:text-2xl font-bold text-slate-900 dark:text-white">Learn SEO &amp; AEO</h2>
                  </div>
                  <img
                    src="data:image/jpeg;base64,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"
                    alt="Deep Audit SEO and AEO"
                    class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                  />
                </div>
                <p class="text-slate-600 dark:text-slate-300 text-sm mb-4">
                  Create content that answers real questions clearly and helps people discover your work.
                </p>
                <div class="space-y-3 mb-5">
                  <div class="p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">🔍 SEO (Search Engine Optimization)</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Make useful content easier for search engines to understand and surface.
                    </p>
                  </div>
                  <div class="p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">🤖 AEO (Answer Engine Optimization)</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Structure helpful answers so answer-driven search experiences can understand and potentially reference your content.
                    </p>
                  </div>
                  <div class="p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                    <h3 class="font-bold text-slate-900 dark:text-white text-sm">🧭 Content strategy</h3>
                    <p class="text-xs text-slate-600 dark:text-slate-300 mt-0.5">
                      Build around audience questions, search intent, original insight, and practical solutions.
                    </p>
                  </div>
                </div>
              </div>
              <button type="button" data-goto="seo-aeo" class="quick-nav-pill w-full btn-secondary-doc py-2.5 px-4 rounded-xl text-sm flex items-center justify-between">
                <span>→ Open the SEO &amp; AEO Playbook</span>
                <span class="font-mono text-xs">OPEN PLAYBOOK</span>
              </button>
            </div>
          </section>

        <!-- =================================================================
             MEMBERSHIP & ABOUT THIS TOOLKIT (ALWAYS VISIBLE AT BOTTOM OF DOC)
             ================================================================= -->
        <section id="section-membership" class="doc-card p-6 sm:p-8 bg-gradient-to-br from-[#FFF7ED] via-white to-[#EFF6FF] dark:from-slate-900 dark:via-slate-900 dark:to-slate-800">
          <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-center">
            <div class="lg:col-span-7 space-y-3">
              <div class="flex items-center gap-3">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Approved Membership"
                  class="w-14 h-14 rounded-xl object-cover border-2 border-white shadow"
                />
                <span class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-wider bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300">
                  🚀 Upcoming Membership
                </span>
              </div>
              <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">Get More From Your Content</h2>
              <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed">
                The free toolkit is designed to help you get started with practical resources you can use right away.
              </p>
              <p class="text-slate-700 dark:text-slate-300 text-sm sm:text-base leading-relaxed">
                Ander Creative's upcoming membership will build on that foundation with expanded prompt collections, additional creative templates, production walkthroughs, and connected content workflows.
              </p>
              <p class="text-orange-700 dark:text-orange-400 font-semibold text-sm sm:text-base">
                Want to hear when it launches? Join the early-access list when registration becomes available.
              </p>
            </div>

            <div class="lg:col-span-5 bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-2xl p-5 shadow-sm">
              <h3 class="font-display text-sm font-bold text-slate-900 dark:text-white mb-3">Join the Early-Access Notification List</h3>
              <form id="earlyAccessForm" class="space-y-3">
                <div>
                  <label for="earlyAccessEmail" class="block text-xs font-medium text-slate-600 dark:text-slate-400 mb-1">Your Best Email</label>
                  <input
                    id="earlyAccessEmail"
                    type="email"
                    required
                    placeholder="creator@yourdomain.com"
                    class="w-full px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-sm text-slate-900 dark:text-white focus:outline-none focus:border-orange-500"
                  />
                </div>
                <div>
                  <label for="earlyAccessFocus" class="block text-xs font-medium text-slate-600 dark:text-slate-400 mb-1">Primary Content Goal</label>
                  <select
                    id="earlyAccessFocus"
                    class="w-full px-3.5 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-sm text-slate-900 dark:text-white focus:outline-none focus:border-orange-500"
                  >
                    <option value="Short-Form Video (Reels / TikTok)">Short-Form Video (Reels / TikTok)</option>
                    <option value="Multi-Asset Content Repurposing">Multi-Asset Content Repurposing</option>
                    <option value="SEO & AEO Searchable Articles">SEO &amp; AEO Searchable Articles</option>
                    <option value="Client Marketing Systems">Client Marketing Systems</option>
                  </select>
                </div>
                <button type="submit" class="w-full btn-primary-orange py-2.5 px-4 rounded-xl text-sm">
                  Join the Early-Access List →
                </button>
                <p id="earlyAccessFeedback" class="hidden text-xs font-mono font-semibold text-emerald-700 dark:text-emerald-400 text-center pt-1"></p>
              </form>
            </div>
          </div>
        </section>

        <!-- =================================================================
             ABOUT THIS TOOLKIT (WITH STOP / WARNING CHARACTER CALLOUT)
             ================================================================= -->
        <section id="section-about" class="doc-card p-6 sm:p-8 space-y-5">
          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
            <div class="flex items-center gap-3.5">
              <img
                src="data:image/jpeg;base64,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"
                alt="ander.creative logo"
                class="w-12 h-12 rounded-full object-cover border-2 border-orange-500"
              />
              <div>
                <h2 class="font-display text-xl font-bold text-slate-900 dark:text-white">About This Toolkit</h2>
                <p class="text-xs font-medium text-orange-600 dark:text-orange-400">Created by @ander.creative. Built to help you go from idea to execution.</p>
              </div>
            </div>
            <span class="text-xs font-mono px-3 py-1 rounded-full bg-[#F3F1EC] dark:bg-slate-800 text-slate-600 dark:text-slate-300">
              Practical Use • Clear Instructions • Repeatable Results
            </span>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-sm text-slate-700 dark:text-slate-300 leading-relaxed">
            <div class="p-4 rounded-xl bg-[#FAF8F5] dark:bg-slate-800/80 border border-[#E5E0D8] dark:border-slate-700">
              <p class="font-bold text-slate-900 dark:text-white mb-1">Curated for Thoughtful Creators</p>
              <p>
                The AI Creative &amp; Marketing Toolkit is a free resource from <strong>@ander.creative</strong> for people who want to use AI more thoughtfully and create marketing content more efficiently.
              </p>
              <p class="mt-2">
                Resources are curated to prioritize practical use, clear instructions, and repeatable results—not simply the number of tools or prompts available.
              </p>
            </div>

            <!-- Stop / Warning Character Callout for Claim & Rights Verification -->
            <div class="notion-callout-warm p-4 flex items-start gap-3.5">
              <img
                src="data:image/jpeg;base64,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"
                alt="Stop and Verify Claims Reminder"
                class="w-16 h-16 rounded-xl object-cover border-2 border-white shadow shrink-0 mt-0.5"
              />
              <div class="text-xs sm:text-sm">
                <span class="font-bold text-orange-800 dark:text-orange-300 uppercase block mb-1">⚠️ Important Verification Reminder</span>
                <p class="text-slate-800 dark:text-slate-200 leading-relaxed">
                  AI tools, features, pricing, and platform policies change. Verify important details before relying on them, review AI-generated claims, and confirm you have the necessary rights to use any templates, media, or other creative assets.
                </p>
              </div>
            </div>
          </div>
        </section>

        </div>

        <!-- =================================================================
             VIEW 2: 01 — CORE AI TOOLS DIRECTORY
             ================================================================= -->
        <div id="view-core-ai-tools" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Comparing Core AI Tools"
                  class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-orange-600 dark:text-orange-400">Section 01 // Curated Directory</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">01 — Core AI Tools Directory</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Discover AI tools for research, writing, design, video, and marketing. Compare what each tool does, what it's best for, and where to get started.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- AEO Direct Answer Lead Box -->
            <div class="notion-callout-blue p-4 text-xs sm:text-sm">
              <strong>Which AI tools should content creators start with? (Quick Answer):</strong>
              Instead of subscribing to dozens of apps, build a lean 4-part creator stack: <strong>Perplexity AI</strong> for source-backed audience research, <strong>Claude / ChatGPT</strong> for voice-matched outlining and scripting, <strong>Canva Magic Studio</strong> for repeatable carousels, and <strong>CapCut</strong> for vertical video pacing and captions.
            </div>

            <!-- Radar Chart + Filter Controls -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-center">
              <div class="lg:col-span-5 bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-4">
                <div class="flex items-center justify-between mb-2">
                  <span class="text-xs font-bold uppercase text-slate-600 dark:text-slate-300">Category Impact Comparison</span>
                  <span class="text-[11px] font-mono text-orange-600">Speed vs. Depth</span>
                </div>
                <div class="relative h-60 w-full">
                  <canvas id="toolsRadarChart"></canvas>
                </div>
              </div>

              <div class="lg:col-span-7 space-y-4">
                <input
                  id="toolSearchInput"
                  type="text"
                  placeholder="Search tools by task (e.g., research, scripts, carousel, reels)..."
                  class="w-full px-4 py-2.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 text-sm text-slate-900 dark:text-white focus:outline-none focus:border-orange-500"
                />

                <div class="flex flex-wrap gap-2" id="toolCategoryFilters">
                  <button type="button" data-tool-cat="All" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white">All Categories</button>
                  <button type="button" data-tool-cat="Research" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Research</button>
                  <button type="button" data-tool-cat="Writing" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Writing</button>
                  <button type="button" data-tool-cat="Design" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Design</button>
                  <button type="button" data-tool-cat="Video" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Video</button>
                  <button type="button" data-tool-cat="Marketing" class="tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Marketing</button>
                </div>

                <p class="text-xs text-slate-500 dark:text-slate-400">
                  💡 Click <strong>☆ Add to Stack</strong> on any card below to save it to your personal Notion tool list.
                </p>
              </div>
            </div>

            <!-- Tools Grid -->
            <div id="toolsDirectoryGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4"></div>
          </div>
        </div>

        <!-- =================================================================
             VIEW 3: 02 — COPY-PASTE AI PROMPT LIBRARY
             ================================================================= -->
        <div id="view-prompt-library" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Copy-Paste AI Prompts"
                  class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-orange-600 dark:text-orange-400">Section 02 // Copy-Paste Prompt Library</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">02 — Copy-Paste AI Prompts</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Use practical prompts to brainstorm ideas, write social media posts, develop video scripts, improve marketing copy, and repurpose content.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- Live Variable Customizer -->
            <div class="notion-callout-warm p-5">
              <div class="flex flex-wrap items-center justify-between gap-2 mb-3">
                <span class="text-xs font-bold uppercase tracking-wider text-orange-800 dark:text-orange-300">
                  ✏️ Fill in your details once — every prompt below updates automatically:
                </span>
                <button type="button" id="btnResetPromptVars" class="text-xs font-semibold text-orange-700 dark:text-orange-400 underline">
                  Reset Variables
                </button>
              </div>
              <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                <div>
                  <label for="varTopic" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">Your Topic or Offer</label>
                  <input id="varTopic" type="text" value="AI Content Workflows for Solopreneurs" class="prompt-var-input w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white focus:border-orange-500 focus:outline-none" />
                </div>
                <div>
                  <label for="varAudience" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">Your Target Audience</label>
                  <input id="varAudience" type="text" value="busy creators and small marketing teams" class="prompt-var-input w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white focus:border-orange-500 focus:outline-none" />
                </div>
                <div>
                  <label for="varTone" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">Your Brand Voice</label>
                  <input id="varTone" type="text" value="practical, clear, zero-fluff, encouraging" class="prompt-var-input w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white focus:border-orange-500 focus:outline-none" />
                </div>
              </div>
            </div>

            <!-- Category Filters -->
            <div class="flex flex-wrap gap-2" id="promptCategoryFilters">
              <button type="button" data-prompt-cat="All" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white">All Prompts</button>
              <button type="button" data-prompt-cat="Brainstorm Ideas" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Brainstorm Ideas</button>
              <button type="button" data-prompt-cat="Social Media Posts" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Social Media Posts</button>
              <button type="button" data-prompt-cat="Video Scripts" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Video Scripts</button>
              <button type="button" data-prompt-cat="Marketing Copy" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Marketing Copy</button>
              <button type="button" data-prompt-cat="Repurpose Content" class="prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700">Repurpose Content</button>
            </div>

            <!-- Prompts Grid -->
            <div id="promptsLibraryGrid" class="grid grid-cols-1 md:grid-cols-2 gap-4"></div>
          </div>
        </div>

        <!-- =================================================================
             VIEW 4: 03 — CANVA TEMPLATE LIBRARY
             ================================================================= -->
        <div id="view-canva-templates" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Canva Visual Templates"
                  class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-emerald-700 dark:text-emerald-400">Section 03 // Visual Starting Points</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">03 — Canva Template Library</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Find customizable starting points for social media graphics, educational carousels, content calendars, lead magnets, and other marketing assets.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- Updated Brand Palette Swatches (Matched to New TikTok Profile Pic!) -->
            <div class="bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-4 flex flex-wrap items-center justify-between gap-4">
              <div>
                <span class="text-xs font-bold uppercase text-slate-700 dark:text-slate-200 block">🎨 @ander.creative Brand Kit Swatches (Click to Copy Hex for Canva)</span>
                <p class="text-xs text-slate-500 dark:text-slate-400 mt-0.5">Matched to your updated profile badge &amp; character sheets for non-AI, human-crafted visuals.</p>
              </div>
              <div class="flex flex-wrap items-center gap-2">
                <button type="button" data-copy-hex="#F97316" class="hex-copy-btn flex items-center gap-2 px-3 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3.5 h-3.5 rounded-full bg-[#F97316]"></span>
                  <span>#F97316 (Creator Orange)</span>
                </button>
                <button type="button" data-copy-hex="#CFDDF0" class="hex-copy-btn flex items-center gap-2 px-3 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3.5 h-3.5 rounded-full bg-[#CFDDF0] border border-slate-400"></span>
                  <span>#CFDDF0 (Pearl Sky)</span>
                </button>
                <button type="button" data-copy-hex="#1E242B" class="hex-copy-btn flex items-center gap-2 px-3 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3.5 h-3.5 rounded-full bg-[#1E242B]"></span>
                  <span>#1E242B (Studio Ink)</span>
                </button>
                <button type="button" data-copy-hex="#16A34A" class="hex-copy-btn flex items-center gap-2 px-3 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3.5 h-3.5 rounded-full bg-[#16A34A]"></span>
                  <span>#16A34A (Signal Green)</span>
                </button>
                <button type="button" data-copy-hex="#12181F" class="hex-copy-btn flex items-center gap-2 px-2.5 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3 h-3 rounded-full bg-[#12181F]"></span><span>#12181F (Cyber Slate)</span>
                </button>
                <button type="button" data-copy-hex="#2EE59D" class="hex-copy-btn flex items-center gap-2 px-2.5 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3 h-3 rounded-full bg-[#2EE59D]"></span><span>#2EE59D (Neon Mint)</span>
                </button>
                <button type="button" data-copy-hex="#00E5FF" class="hex-copy-btn flex items-center gap-2 px-2.5 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3 h-3 rounded-full bg-[#00E5FF]"></span><span>#00E5FF (HUD Cyan)</span>
                </button>
                <button type="button" data-copy-hex="#1D2834" class="hex-copy-btn flex items-center gap-2 px-2.5 py-1.5 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs font-mono hover:border-orange-500">
                  <span class="w-3 h-3 rounded-full bg-[#1D2834]"></span><span>#1D2834 (Panel Navy)</span>
                </button>
              </div>
            </div>

            <div id="canvaTemplatesGrid" class="grid grid-cols-1 md:grid-cols-2 gap-5"></div>
          </div>
        </div>

        <!-- =================================================================
             VIEW 5: 04 — CAPCUT TEMPLATE LIBRARY
             ================================================================= -->
        <div id="view-capcut-templates" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="CapCut Video Templates"
                  class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-orange-600 dark:text-orange-400">Section 04 // Vertical Video Formats</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">04 — CapCut Template Library</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Explore repeatable short-form video formats, editing recipes, caption styles, and production ideas for TikTok, Instagram Reels, and other vertical video platforms.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- Short-Form Retention & Pacing Graph -->
            <div class="bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-5">
              <div class="flex flex-wrap items-center justify-between gap-2 mb-3">
                <div>
                  <span class="text-xs font-bold uppercase text-orange-600 dark:text-orange-400">📈 Short-Form Retention Pacing Curve (TikTok &amp; Reels)</span>
                  <p class="text-xs text-slate-600 dark:text-slate-400">How structured hook + pattern-interrupt beats keep viewers watching past the 3-second mark</p>
                </div>
                <span class="text-xs font-mono font-bold px-2.5 py-1 rounded bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300">
                  Target: &gt;68% 3-Second Hold
                </span>
              </div>
              <div class="relative h-60 w-full">
                <canvas id="capcutRetentionChart"></canvas>
              </div>
            </div>

            <div id="capcutTemplatesGrid" class="grid grid-cols-1 md:grid-cols-2 gap-5"></div>
          </div>
        </div>

        <!-- =================================================================
             VIEW 6: CONTENT CREATION WORKFLOWS (INTERACTIVE BLUEPRINT STUDIO)
             ================================================================= -->
        <div id="view-workflows" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="Featured Content Creation Workflows"
                  class="w-16 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-orange-600 dark:text-orange-400">Complete Process Blueprints</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">Featured Content Creation Workflows</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Start with a complete process instead of collecting disconnected tools. Select any workflow below to check off steps or copy to Notion.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- Workflow Selector Cards -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-3.5">
              <button type="button" data-wf-tab="short-form" class="wf-selector-btn text-left p-4 rounded-xl border-2 border-orange-600 bg-orange-50/70 dark:bg-orange-950/30 transition">
                <span class="font-mono text-xs font-bold text-orange-700 dark:text-orange-400 uppercase block mb-1">Workflow 01</span>
                <p class="font-display font-bold text-slate-900 dark:text-white text-base">Idea to Short-Form Video</p>
                <p class="text-xs text-slate-600 dark:text-slate-300 mt-1">Turn one audience question into a hook, script, shot list, and edited video.</p>
              </button>
              <button type="button" data-wf-tab="multi-asset" class="wf-selector-btn text-left p-4 rounded-xl border border-[#E5E0D8] dark:border-slate-700 bg-[#FAF8F5] dark:bg-slate-800 hover:border-orange-500 transition">
                <span class="font-mono text-xs font-bold text-slate-500 uppercase block mb-1">Workflow 02</span>
                <p class="font-display font-bold text-slate-900 dark:text-white text-base">One Idea, Multiple Assets</p>
                <p class="text-xs text-slate-600 dark:text-slate-300 mt-1">Repurpose one useful topic into a carousel, video, caption, and email.</p>
              </button>
              <button type="button" data-wf-tab="searchable-article" class="wf-selector-btn text-left p-4 rounded-xl border border-[#E5E0D8] dark:border-slate-700 bg-[#FAF8F5] dark:bg-slate-800 hover:border-orange-500 transition">
                <span class="font-mono text-xs font-bold text-slate-500 uppercase block mb-1">Workflow 03</span>
                <p class="font-display font-bold text-slate-900 dark:text-white text-base">Question to Searchable Article</p>
                <p class="text-xs text-slate-600 dark:text-slate-300 mt-1">Develop a content brief, create a draft, verify claims, and optimize the final article.</p>
              </button>
            </div>

            <!-- Active Workflow Blueprint Container -->
            <div id="activeWorkflowDetail" class="bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-5 sm:p-6"></div>
          </div>
        </div>

        <!-- =================================================================
             VIEW 7: LEARN SEO & AEO PLAYBOOK FOR CREATORS (WITH 2026 BEST PRACTICES)
             ================================================================= -->
        <div id="view-seo-aeo" class="tab-view hidden space-y-6">
          <div class="doc-card p-6 sm:p-8 space-y-6">
            <div class="flex flex-wrap items-center justify-between gap-4 border-b border-[#E5E0D8] dark:border-slate-700 pb-4">
              <div class="flex items-center gap-3.5">
                <img
                  src="data:image/jpeg;base64,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"
                  alt="SEO & AEO Deep Audit"
                  class="w-14 h-14 rounded-xl object-cover border border-slate-700 shrink-0"
                />
                <div>
                  <span class="font-mono text-xs font-bold uppercase text-emerald-700 dark:text-emerald-400">Discoverability Playbook</span>
                  <h2 class="font-display text-2xl sm:text-3xl font-extrabold text-slate-900 dark:text-white">SEO &amp; AEO Playbook for Creators</h2>
                  <p class="text-slate-600 dark:text-slate-300 text-sm">
                    Create content that answers real questions clearly and helps people discover your work.
                  </p>
                </div>
              </div>
              <button type="button" data-goto="start-here" class="quick-nav-pill btn-secondary-doc px-3 py-1.5 rounded-lg text-xs">
                ← Back to Start Here
              </button>
            </div>

            <!-- AEO Direct Answer Lead (48 Words — Self-Contained Citation Block) -->
            <div class="notion-callout-sage p-4 text-xs sm:text-sm">
              <strong>What is the difference between SEO and AEO for creators? (Direct Answer):</strong>
              <strong>SEO</strong> helps your page rank in traditional search engine results for clicks, while <strong>AEO (Answer Engine Optimization)</strong> structures your content with question-based headings, concise 40–60 word direct answers, and original proof so AI platforms (like ChatGPT, Perplexity, and Google AI Overviews) trust and cite your work directly.
            </div>

            <!-- 3 Core Pillars + Ranking Signals Graph -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-center">
              <div class="lg:col-span-6 space-y-3.5">
                <div class="p-4 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                  <span class="font-mono text-xs font-bold text-orange-600 uppercase">Pillar 01 // Search Engine Optimization</span>
                  <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mt-0.5">SEO</h3>
                  <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mt-1">
                    Make useful content easier for search engines to understand and surface. Use sequential heading hierarchy (`H2 → H3`), descriptive titles, and internal links across related topics.
                  </p>
                </div>
                <div class="p-4 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                  <span class="font-mono text-xs font-bold text-emerald-700 dark:text-emerald-400 uppercase">Pillar 02 // Answer Engine Optimization</span>
                  <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mt-0.5">AEO</h3>
                  <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mt-1">
                    Structure helpful answers so answer-driven search experiences can understand and potentially reference your content. Pages with clear heading hierarchy and direct answer blocks earn up to <strong>2.8x more AI citations</strong>.
                  </p>
                </div>
                <div class="p-4 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
                  <span class="font-mono text-xs font-bold text-blue-700 dark:text-blue-400 uppercase">Pillar 03 // Durable Authority</span>
                  <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mt-0.5">Content strategy</h3>
                  <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mt-1">
                    Build around audience questions, search intent, original insight, and practical solutions. First-party creator examples and real benchmarks earn citations that generic AI summaries cannot copy.
                  </p>
                </div>
              </div>

              <div class="lg:col-span-6 bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-5">
                <div class="flex items-center justify-between mb-2">
                  <span class="text-xs font-bold uppercase text-slate-700 dark:text-slate-200">SEO vs. AEO Signal Weighting</span>
                  <span class="text-xs font-mono text-emerald-700 dark:text-emerald-400 font-semibold">2026 Creator Benchmark</span>
                </div>
                <div class="relative h-64 w-full">
                  <canvas id="seoAeoChart"></canvas>
                </div>
              </div>
            </div>

            <!-- Scannable SEO vs AEO Comparison Table (Best Practice #3: Tables for Decisions) -->
            <div class="overflow-x-auto rounded-xl border border-[#E5E0D8] dark:border-slate-700">
              <table class="w-full text-left border-collapse text-xs sm:text-sm">
                <thead>
                  <tr class="bg-[#F3F1EC] dark:bg-slate-800 text-slate-800 dark:text-slate-200 border-b border-[#E5E0D8] dark:border-slate-700">
                    <th class="py-3 px-4 font-bold">Dimension</th>
                    <th class="py-3 px-4 font-bold text-orange-700 dark:text-orange-400">Traditional SEO</th>
                    <th class="py-3 px-4 font-bold text-emerald-700 dark:text-emerald-400">Answer Engine Optimization (AEO)</th>
                    <th class="py-3 px-4 font-bold">Creator Action Item</th>
                  </tr>
                </thead>
                <tbody class="divide-y divide-[#E5E0D8] dark:divide-slate-700 bg-white dark:bg-slate-900">
                  <tr>
                    <td class="py-3 px-4 font-semibold">Primary Goal</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">Rank in search results to earn clicks</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">Be extracted, quoted, and cited in AI answers</td>
                    <td class="py-3 px-4 text-slate-700 dark:text-slate-200">Put the 40–60 word answer right under the H2</td>
                  </tr>
                  <tr>
                    <td class="py-3 px-4 font-semibold">Target Input</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">Short keywords (e.g., "video hooks")</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">Conversational questions ("How do I write a 3-second Reel hook?")</td>
                    <td class="py-3 px-4 text-slate-700 dark:text-slate-200">Phrase H2/H3 headings as exact audience questions</td>
                  </tr>
                  <tr>
                    <td class="py-3 px-4 font-semibold">Trust Signals</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">Backlinks &amp; keyword placement</td>
                    <td class="py-3 px-4 text-slate-600 dark:text-slate-300">First-party proof, clear tables/steps, visible FAQ structure, freshness</td>
                    <td class="py-3 px-4 text-slate-700 dark:text-slate-200">Include 1 original test result or creator example per post</td>
                  </tr>
                </tbody>
              </table>
            </div>

            <!-- Interactive AEO Answer Block Builder + Live Word Count Grader -->
            <div class="bg-[#FAF8F5] dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-5 sm:p-6 space-y-4">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <div>
                  <span class="text-xs font-bold uppercase text-orange-600 dark:text-orange-400">🛠️ Interactive AEO Answer Block Builder &amp; Grader</span>
                  <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white">Draft an Extractable Answer Block for Your Next Post</h3>
                </div>
                <div class="flex items-center gap-2">
                  <span id="aeoWordCountBadge" class="text-xs font-mono font-bold px-2.5 py-1 rounded-lg bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300">
                    32 words • Optimal AEO Length
                  </span>
                  <button type="button" id="btnCopyAeoBlock" class="btn-primary-orange px-4 py-2 rounded-lg text-xs">
                    Copy Formatted Notion Block
                  </button>
                </div>
              </div>
              <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div>
                  <label for="aeoQuestion" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">1. Exact Audience Question (H2 Heading)</label>
                  <input id="aeoQuestion" type="text" value="How do I repurpose one video idea into multiple marketing assets?" class="w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white" />
                </div>
                <div>
                  <label for="aeoDirectAnswer" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">2. Direct 40–60 Word Answer Lead (AEO Snippet)</label>
                  <input id="aeoDirectAnswer" type="text" value="Start with a core 60-second video script answering one audience question, then extract the hook and three key points into an educational Canva carousel, a short-form Reel, and a value-focused newsletter email so every platform gets a native asset from a single research session." class="w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white" />
                </div>
                <div>
                  <label for="aeoProof" class="block text-xs font-semibold text-slate-700 dark:text-slate-300 mb-1">3. Original Creator Insight / First-Party Proof</label>
                  <input id="aeoProof" type="text" value="Batch-record 3 hooks at once so you can test retention while keeping the core educational body identical." class="w-full px-3 py-2 rounded-lg bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 text-xs sm:text-sm text-slate-900 dark:text-white" />
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- =================================================================
             SEPARATE PAGE FOOTER PAGINATION (PREVIOUS / HOME / NEXT PAGE)
             ================================================================= -->
        <div id="subpagePaginationBar" class="doc-card p-4 sm:p-5 flex flex-wrap items-center justify-between gap-3 bg-white dark:bg-slate-900">
          <button type="button" id="btnPrevPage" class="btn-secondary-doc px-4 py-2 rounded-xl text-xs sm:text-sm flex items-center gap-2">
            <span>←</span>
            <span id="prevPageLabel">Start Here</span>
          </button>
          <div class="flex items-center gap-2 text-xs font-mono text-slate-500 dark:text-slate-400">
            <span id="currentPageIndicator">Page 1 of 7</span>
          </div>
          <button type="button" id="btnNextPage" class="btn-primary-orange px-4 py-2 rounded-xl text-xs sm:text-sm flex items-center gap-2">
            <span id="nextPageLabel">Next: 01 — Core AI Tools</span>
            <span>→</span>
          </button>
        </div>
      </main>
    </div>
  </div>

  <!-- Footer -->
  <footer class="border-t border-[#E5E0D8] dark:border-slate-800 bg-white dark:bg-[#181B20] py-6 mt-12">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs text-slate-500 dark:text-slate-400">
      <div class="flex items-center gap-2.5">
        <img src="data:image/jpeg;base64,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" alt="ander.creative" class="w-6 h-6 rounded-full object-cover" />
        <span>Created by <strong class="text-slate-900 dark:text-white">@ander.creative</strong>. Built to help you go from idea to execution.</span>
      </div>
      <div class="flex items-center gap-4 font-medium">
        <button type="button" data-goto="start-here" class="quick-nav-pill hover:text-orange-600">Start Here</button>
        <button type="button" data-goto="core-ai-tools" class="quick-nav-pill hover:text-orange-600">Tools</button>
        <button type="button" data-goto="prompt-library" class="quick-nav-pill hover:text-orange-600">Prompts</button>
        <button type="button" data-goto="workflows" class="quick-nav-pill hover:text-orange-600">Workflows</button>
      </div>
    </div>
  </footer>

  <!-- =====================================================================
       MODAL 1: SAVED TOOL STACK DRAWER
       ===================================================================== -->
  <div id="modalSavedStack" class="fixed inset-0 z-50 hidden bg-slate-950/60 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="doc-card max-w-lg w-full p-6 space-y-4">
      <div class="flex items-center justify-between border-b border-[#E5E0D8] dark:border-slate-700 pb-3">
        <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white">★ My Saved Creator Stack</h3>
        <button type="button" id="closeSavedStack" class="text-slate-500 hover:text-slate-900 dark:hover:text-white font-mono text-sm px-2 py-1">✕ ESC</button>
      </div>
      <p class="text-xs text-slate-600 dark:text-slate-300">Tools bookmarked from the Core AI Tools directory for your active workflow:</p>
      <div id="savedStackList" class="space-y-2 max-h-72 overflow-y-auto"></div>
      <div class="flex justify-end gap-2 pt-2 border-t border-[#E5E0D8] dark:border-slate-700">
        <button type="button" id="btnCopyStackMarkdown" class="btn-primary-orange px-4 py-2 rounded-lg text-xs">Copy Stack to Notion Markdown</button>
      </div>
    </div>
  </div>

  <!-- =====================================================================
       MODAL 2: NOTION EMBED & SETUP GUIDE
       ===================================================================== -->
  <div id="modalNotionGuide" class="fixed inset-0 z-50 hidden bg-slate-950/60 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="doc-card max-w-2xl w-full p-6 space-y-4">
      <div class="flex items-center justify-between border-b border-[#E5E0D8] dark:border-slate-700 pb-3">
        <div>
          <span class="text-xs font-mono font-bold text-orange-600 uppercase">Notion Doc Integration</span>
          <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white">How to Embed or Paste This Hub in Notion</h3>
        </div>
        <button type="button" id="closeNotionGuide" class="text-slate-500 hover:text-slate-900 dark:hover:text-white font-mono text-sm px-2 py-1">✕ ESC</button>
      </div>
      <div class="space-y-3 text-xs sm:text-sm text-slate-700 dark:text-slate-300 leading-relaxed">
        <div class="p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
          <p class="font-bold text-orange-700 dark:text-orange-400 mb-1">1. Embed as an Interactive Notion Doc Block (/embed)</p>
          <p>Host this single HTML file on GitHub Pages, Netlify Drop, or Cloudflare Pages, then type <code class="px-1.5 py-0.5 rounded bg-orange-100 dark:bg-slate-900 text-orange-800 dark:text-orange-300 font-mono">/embed</code> inside Notion and paste the link. Because it defaults to <strong>Full Notion Doc Mode</strong> with warm paper colors, it blends seamlessly into a standard Notion page.</p>
        </div>
        <div class="p-3.5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
          <p class="font-bold text-emerald-700 dark:text-emerald-400 mb-1">2. Copy Native Notion Markdown Structure</p>
          <p>Want to paste the text, callout blocks, and checklists directly as native Notion blocks? Click the button below and paste (`Ctrl+V` / `Cmd+V`) right into any Notion page.</p>
        </div>
      </div>
      <div class="flex flex-wrap items-center justify-end gap-3 pt-3 border-t border-[#E5E0D8] dark:border-slate-700">
        <button type="button" id="btnCopyNotionMarkdown" class="btn-primary-orange px-4 py-2 rounded-lg text-xs">
          📋 Copy Complete Notion Markdown Structure
        </button>
      </div>
    </div>
  </div>

  <!-- Toast Notification -->
  <div id="toastBanner" class="fixed bottom-5 right-5 z-50 hidden bg-slate-900 text-white px-4 py-3 rounded-xl shadow-xl flex items-center gap-2.5 text-xs font-medium">
    <span class="w-2.5 h-2.5 rounded-full bg-orange-500"></span>
    <span id="toastMessage">Copied to clipboard!</span>
  </div>

  <script>
    // =========================================================================
    // STATE & DATA STORE (CONSISTENT WITH @ANDER.CREATIVE TOOLKIT)
    // =========================================================================
    const state = {
      docMode: 'tabbed', // 'tabbed' shows separate pages (default); 'full' shows all sections in one scroll
      activeTab: 'start-here',
      completedSteps: [1, 2],
      savedTools: ['Perplexity AI', 'Claude 3.7 / ChatGPT', 'Canva Magic Studio', 'CapCut Pro'],
      selectedToolCat: 'All',
      selectedPromptCat: 'All',
      activeWorkflow: 'short-form'
    };

    const stepRecommendations = {
      1: {
        badge: 'ACTIVE STAGE: 01. RESEARCH',
        text: 'Identify a real question, problem, or need your audience has using search intent & audience comments.',
        target: 'core-ai-tools',
        btnText: 'Explore Research Tools →'
      },
      2: {
        badge: 'ACTIVE STAGE: 02. CREATE',
        text: 'Use a Copy-Paste AI prompt to develop the idea, outline, script, or first draft in your brand voice.',
        target: 'prompt-library',
        btnText: 'Open Prompt Library →'
      },
      3: {
        badge: 'ACTIVE STAGE: 03. DESIGN',
        text: 'Choose a customizable Canva template for carousels, graphics, or lead magnets with consistent brand colors.',
        target: 'canva-templates',
        btnText: 'Browse Canva Templates →'
      },
      4: {
        badge: 'ACTIVE STAGE: 04. PRODUCE',
        text: 'Apply a repeatable CapCut short-form editing recipe, dynamic captions, and retention pacing cuts.',
        target: 'capcut-templates',
        btnText: 'Open CapCut Recipes →'
      },
      5: {
        badge: 'ACTIVE STAGE: 05. PUBLISH',
        text: 'Adapt your asset to the platform, structure direct answers for SEO/AEO, and give a clear next step.',
        target: 'seo-aeo',
        btnText: 'Open SEO & AEO Playbook →'
      },
      6: {
        badge: 'ACTIVE STAGE: 06. IMPROVE',
        text: 'Review 3-second hold rate, saves, and search impressions to refine the next iteration of your workflow.',
        target: 'workflows',
        btnText: 'Review Workflow Blueprints →'
      }
    };

    const coreToolsData = [
      {
        name: 'Perplexity AI',
        category: 'Research',
        whatItDoes: 'Real-time citation-backed answer engine that surfaces what questions your audience is asking and links to primary sources.',
        bestFor: 'Step 01 Research — validating claims and uncovering real questions before you write.',
        getStarted: 'Search your core topic and inspect the follow-up questions & cited sources.'
      },
      {
        name: 'Claude 3.7 / ChatGPT',
        category: 'Writing',
        whatItDoes: 'Conversational AI assistants for turning rough notes into structured outlines, video scripts, and multi-asset drafts.',
        bestFor: 'Step 02 Create — developing stronger ideas and first drafts without sounding robotic.',
        getStarted: 'Paste 2 examples of your own writing alongside a Prompt Library template.'
      },
      {
        name: 'Canva Magic Studio',
        category: 'Design',
        whatItDoes: 'Visual design workspace with Brand Kits, reusable carousel layouts, lead magnet templates, and 1-click resizing.',
        bestFor: 'Step 03 Design — creating polished carousels and graphics without designing from scratch.',
        getStarted: 'Save your #F97316, #CFDDF0, and #1E242B brand colors in Canva Brand Kit.'
      },
      {
        name: 'CapCut Desktop & Mobile',
        category: 'Video',
        whatItDoes: 'Short-form video editor with auto-captions, hook pacing presets, beat markers, and vertical layout templates.',
        bestFor: 'Step 04 Produce — editing TikToks, Reels, and Shorts faster and more consistently.',
        getStarted: 'Start with Recipe 01 (Question → 3-Step Visual Breakdown).'
      },
      {
        name: 'Notion Content OS',
        category: 'Marketing',
        whatItDoes: 'All-in-one document and database workspace to organize your ideas, prompts, templates, and publishing checklist.',
        bestFor: 'Step 05 Publish & Step 06 Improve — keeping your entire workflow repeatable in one place.',
        getStarted: 'Copy any Featured Workflow checklist directly into your Notion weekly planner.'
      },
      {
        name: 'AnswerThePublic / AlsoAsked',
        category: 'Research',
        whatItDoes: 'Visualizes exact "People Also Ask" and conversational search questions around any keyword or niche.',
        bestFor: 'SEO & AEO Playbook — phrasing your H2 headings around exact audience questions.',
        getStarted: 'Pick 3 "How" or "Why" questions to structure your next article or video.'
      }
    ];

    const promptsData = [
      {
        id: 'p1',
        title: 'Audience Question & Hook Matrix',
        category: 'Brainstorm Ideas',
        useCase: 'Turn a broad topic into 5 concrete audience questions and scroll-stopping hooks.',
        template: `Act as a senior content strategist for [Audience]. I am creating content about [Topic] in a [Tone] voice.\n\n1. List the top 5 specific, urgent questions [Audience] ask right before trying to solve this problem.\n2. For each question, write one curiosity-gap hook (under 12 words) and one myth-busting hook.\n3. Highlight which question has the highest potential for a 60-second short-form video.`
      },
      {
        id: 'p2',
        title: '60-Second Short-Form Video Script (Hook-Value-CTA)',
        category: 'Video Scripts',
        useCase: 'Draft a tight vertical video script with visual B-roll cues for Reels & TikTok.',
        template: `Write a 60-second vertical video script about [Topic] tailored for [Audience] using a [Tone] tone.\n\nStructure the script as a 2-column table (Spoken Audio | Visual / CapCut B-Roll Cue):\n- 0:00–0:03 Hook: Direct pattern interrupt addressing the core problem.\n- 0:03–0:15 Context: Why common advice falls short.\n- 0:15–0:48 3 Actionable Steps: Clear, repeatable steps.\n- 0:48–0:60 Next Step CTA: Clear takeaway and invitation to save or comment.`
      },
      {
        id: 'p3',
        title: '7-Slide Educational Carousel Architect',
        category: 'Social Media Posts',
        useCase: 'Structure a high-save Instagram / LinkedIn carousel mapped to Canva slides.',
        template: `Create a 7-slide educational carousel outline on [Topic] for [Audience] in a [Tone] style.\n\n- Slide 1 (Cover): Bold 6-word headline + subtitle promise.\n- Slide 2 (The Problem): Why most people get stuck.\n- Slides 3–5 (The System): 1 actionable step per slide (Headline + 25-word explanation + visual graphic suggestion).\n- Slide 6 (Quick Summary Checklist): 4 bullet takeaways.\n- Slide 7 (CTA): Clear next step for the reader.`
      },
      {
        id: 'p4',
        title: 'One Idea → 4 Marketing Assets Repurposer',
        category: 'Repurpose Content',
        useCase: 'Transform one core insight or transcript into a carousel, video hook, caption, and email.',
        template: `Take the core topic "[Topic]" for [Audience] (Voice: [Tone]) and repurpose it into 4 connected marketing assets:\n1. Short-Form Video Hook + 3 talking points.\n2. 5-Slide Carousel slide-by-slide copy.\n3. Platform-native social caption (120 words max with skimmable spacing).\n4. Short value-first newsletter email (Subject line + 150-word body + 1 clear next-step link).`
      },
      {
        id: 'p5',
        title: 'SEO & AEO Searchable Article Brief + Answer Lead',
        category: 'Marketing Copy',
        useCase: 'Structure an article that ranks in traditional search and gets cited by AI answer engines.',
        template: `Create an SEO & AEO content brief on "[Topic]" for [Audience] in a [Tone] tone:\n1. Primary Search Intent & Target Question-Based H2.\n2. Direct Answer Block (40–55 words max that directly answers the core question in plain language right below the heading).\n3. H2/H3 Question Tree Outline covering follow-up questions.\n4. 3 places where I should insert original creator proof, benchmarks, or workflow examples.`
      },
      {
        id: 'p6',
        title: 'Human Editorial Copy Polisher (Anti-AI Tone)',
        category: 'Marketing Copy',
        useCase: 'Strip out generic AI buzzwords so your draft reads like a real, thoughtful human creator.',
        template: `Review my draft about [Topic] for [Audience]. Rewrite it in a [Tone] voice following these rules:\n- Remove generic AI clichés ("delve", "unlock", "game-changer", "in today's fast-paced world").\n- Front-load the practical answer in the first two sentences.\n- Provide 2 variations: Option A (Direct & Actionable) and Option B (Story-Led & Conversational).`
      }
    ];

    const canvaTemplatesData = [
      {
        title: '7-Slide Educational Carousel Blueprint',
        format: '1080 × 1350 px (4:5 Portrait)',
        category: 'Educational Carousels',
        description: 'Warm, high-contrast editorial carousel with bold Tangerine step badges, clean reading hierarchy, and a saveable summary checklist on Slide 6.',
        structure: ['Slide 1: Question Hook Headline + Character Reaction Badge', 'Slides 2–5: 1 Step per Slide (Max 28 words + Visual Diagram)', 'Slide 6: Full 6-Step System Cheat Sheet', 'Slide 7: @ander.creative Sign-Off + Clear Next Step']
      },
      {
        title: 'Creator Comparison & Tool Scorecard Graphic',
        format: '1080 × 1350 px / 1920 × 1080 px',
        category: 'Social Media Graphics',
        description: 'Side-by-side decision table comparing 4 AI tools across Best Use Case, Setup Speed, and Output Quality.',
        structure: ['Top Header: Audience Question + Quick Summary', 'Center Grid: 4 Tool Cards with Clear "Best For" Badges', 'Bottom Bar: "Start Here If..." Decision Guide']
      },
      {
        title: 'Multi-Channel Content Calendar & Sprint Board',
        format: '1920 × 1080 px (16:9 Notion Cover / Board)',
        category: 'Content Calendars',
        description: 'Weekly visual production board mapping 1 Core Pillar Idea across Short-Form Video, Carousel, Article, and Newsletter slots.',
        structure: ['Left Column: Weekly Audience Question & Pillar Topic', 'Middle Columns: Mon–Fri Asset Status (Research → Publish)', 'Right Column: Retention & Search Citation Tracker']
      },
      {
        title: '5-Page Actionable Playbook & Lead Magnet PDF',
        format: '8.5 × 11 in / A4 Printable & Mobile-Ready',
        category: 'Lead Magnets',
        description: 'Clean, reader-friendly resource guide template for turning your best workflows or prompt packs into an email opt-in asset.',
        structure: ['Page 1: Cover with Profile Badge & Value Promise', 'Page 2: Quick-Start 6-Step Workflow Map', 'Pages 3–4: Copy-Paste Prompts & Checklists', 'Page 5: Next Steps & Early-Access Invitation']
      }
    ];

    const capcutTemplatesData = [
      {
        title: 'Recipe 01: Question → 3-Step Visual Breakdown',
        duration: '38–50 Seconds (9:16 Vertical)',
        style: 'Talking Head + Clean Screen-Recording Callouts',
        description: 'Opens with a real audience question overlay in the first 2.5 seconds, followed by 3 clear visual steps.',
        beats: ['0:00–0:03: Question Badge Pop-Up + Direct Hook', '0:03–0:15: Step 1 with Bold Tangerine Lower-Third Title', '0:15–0:35: Steps 2 & 3 with Tight J-Cut Audio Pacing', '0:35–0:45: Final Result Preview + Clear Next Step CTA']
      },
      {
        title: 'Recipe 02: Blank Page vs. Repeatable System Split',
        duration: '25–35 Seconds (9:16 Vertical)',
        style: 'Top/Bottom Split or Green-Screen Walkthrough',
        description: 'Contrasts staring at a blank page with running your structured 6-step AI workflow in real time.',
        beats: ['0:00–0:02.5: Side-by-side Hook ("Stop prompting AI like this...")', '0:02.5–0:18: Live Prompt + Canva Template Walkthrough', '0:18–0:30: Final Asset Comparison + Save Prompt']
      },
      {
        title: 'Recipe 03: High-Legibility Safe-Zone Caption Preset',
        duration: 'Universal Preset (TikTok / Reels / Shorts)',
        style: 'Plus Jakarta Sans Bold + #F97316 Active Keyword Highlight',
        description: 'Clean, eye-level caption styling positioned inside the safe zone above platform buttons so text is always easy to read.',
        beats: ['Font: Bold Sans-Serif, Max 2 Lines per Screen', 'Active Keyword Highlight: #F97316 (Orange) & #FFFFFF (White)', 'Safe-Zone Placement: Centered 35% from bottom edge']
      },
      {
        title: 'Recipe 04: 15-Second B-Roll + Saveable Checklist Reel',
        duration: '12–18 Seconds (High Save-Rate Format)',
        style: 'Workspace B-Roll + On-Screen Step List',
        description: 'Pairs calm workspace footage with a 5-point on-screen checklist that viewers pause and save for later.',
        beats: ['0:00–0:02: Bold Question Headline + Audio Beat', '0:02–0:12: Timed Reveal of 5 Practical Steps', '0:12–0:15: Clean Loop Transition + Caption Read Prompt']
      }
    ];

    const workflowsDetailData = {
      'short-form': {
        title: 'Idea to Short-Form Video',
        subtitle: 'Turn one audience question into a hook, script, shot list, and edited video.',
        multiplier: '45 Min End-to-End',
        steps: [
          '1. Isolate 1 specific question from audience comments or Perplexity search intent.',
          '2. Run the "60-Second Short-Form Video Script" prompt in the Prompt Library to generate 3 hooks and a 2-column audio/visual script.',
          '3. Record A-roll talking points in batches (record 2 hook variations for the first 3 seconds).',
          '4. Drop clips into CapCut Recipe 01, apply the safe-zone caption preset, and add 3 visual screen-recording callouts.',
          '5. Publish to Reels/TikTok/Shorts with a clear next step for viewers.'
        ]
      },
      'multi-asset': {
        title: 'One Idea, Multiple Assets',
        subtitle: 'Repurpose one useful topic into a carousel, video, caption, and email.',
        multiplier: '1 Topic → 4 Publishable Assets',
        steps: [
          '1. Start with one validated topic that solves a real problem for your audience.',
          '2. Run the "One Idea → 4 Marketing Assets Repurposer" prompt to extract tailored angles for each format.',
          '3. Drop the 7-slide outline into the Canva Educational Carousel Blueprint.',
          '4. Record a 45-second companion Reel summarizing slides 2–5.',
          '5. Schedule the social caption and send the 150-word value email to your list.'
        ]
      },
      'searchable-article': {
        title: 'Question to Searchable Article',
        subtitle: 'Develop a content brief, create a draft, verify claims, and optimize the final article.',
        multiplier: 'SEO + AEO Evergreen Asset',
        steps: [
          '1. Identify primary search intent and 4 follow-up "People Also Ask" questions.',
          '2. Generate an SEO & AEO Content Brief with a direct 40–60 word answer block right under the main question H2.',
          '3. Draft the article section by section, weaving in your own creator workflow examples and proof.',
          '4. Verify all tool features, pricing, and factual claims before publishing.',
          '5. Add internal links to your related templates and review search/citation impressions quarterly.'
        ]
      }
    };

    // =========================================================================
    // TOAST & CLIPBOARD HELPERS
    // =========================================================================
    let toastTimer = null;
    function showToast(msg) {
      const banner = document.getElementById('toastBanner');
      const text = document.getElementById('toastMessage');
      if (!banner || !text) return;
      text.textContent = msg;
      banner.classList.remove('hidden');
      if (toastTimer) clearTimeout(toastTimer);
      toastTimer = setTimeout(() => {
        banner.classList.add('hidden');
      }, 2800);
    }

    function copyTextToClipboard(text, successMsg) {
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(text).then(() => {
          showToast(successMsg || 'Copied to clipboard!');
        }).catch(() => {
          fallbackCopy(text, successMsg);
        });
      } else {
        fallbackCopy(text, successMsg);
      }
    }

    function fallbackCopy(text, successMsg) {
      const ta = document.createElement('textarea');
      ta.value = text;
      ta.style.position = 'fixed';
      ta.style.opacity = '0';
      document.body.appendChild(ta);
      ta.select();
      try {
        document.execCommand('copy');
        showToast(successMsg || 'Copied to clipboard!');
      } catch (e) {
        showToast('Ready to copy!');
      }
      document.body.removeChild(ta);
    }

    // =========================================================================
    // NAVIGATION & VIEW MODE (FULL NOTION DOC SCROLL VS TABBED FOCUS)
    // =========================================================================
    function applyDocModeUI() {
      const btnFull = document.getElementById('btnModeFullDoc');
      const btnTab = document.getElementById('btnModeTabbed');
      if (state.docMode === 'full') {
        if (btnFull) btnFull.className = 'px-2.5 py-1 rounded-md font-semibold bg-white dark:bg-slate-900 text-orange-700 dark:text-orange-400 shadow-sm transition';
        if (btnTab) btnTab.className = 'px-2.5 py-1 rounded-md font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition';
        document.querySelectorAll('.tab-view').forEach(view => view.classList.remove('hidden'));
      } else {
        if (btnTab) btnTab.className = 'px-2.5 py-1 rounded-md font-semibold bg-white dark:bg-slate-900 text-orange-700 dark:text-orange-400 shadow-sm transition';
        if (btnFull) btnFull.className = 'px-2.5 py-1 rounded-md font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition';
        document.querySelectorAll('.tab-view').forEach(view => view.classList.add('hidden'));
        const activeEl = document.getElementById('view-' + state.activeTab);
        if (activeEl) activeEl.classList.remove('hidden');
      }
    }

    const pageOrder = [
      { id: 'start-here', title: 'Start Here (Home Hub)' },
      { id: 'core-ai-tools', title: '01 — Core AI Tools' },
      { id: 'prompt-library', title: '02 — Prompt Library' },
      { id: 'canva-templates', title: '03 — Canva Templates' },
      { id: 'capcut-templates', title: '04 — CapCut Templates' },
      { id: 'workflows', title: 'Content Creation Workflows' },
      { id: 'seo-aeo', title: 'SEO & AEO Playbook' }
    ];

    function updatePaginationUI() {
      const idx = pageOrder.findIndex(p => p.id === state.activeTab);
      const curIdx = idx >= 0 ? idx : 0;
      const ind = document.getElementById('currentPageIndicator');
      if (ind) ind.textContent = `Page ${curIdx + 1} of ${pageOrder.length} • ${pageOrder[curIdx].title}`;

      const prevBtn = document.getElementById('btnPrevPage');
      const prevLbl = document.getElementById('prevPageLabel');
      const nextBtn = document.getElementById('btnNextPage');
      const nextLbl = document.getElementById('nextPageLabel');

      const prevPage = pageOrder[(curIdx - 1 + pageOrder.length) % pageOrder.length];
      const nextPage = pageOrder[(curIdx + 1) % pageOrder.length];

      if (prevLbl) prevLbl.textContent = prevPage.title;
      if (prevBtn) prevBtn.setAttribute('data-goto-page', prevPage.id);
      if (nextLbl) nextLbl.textContent = `Next: ${nextPage.title}`;
      if (nextBtn) nextBtn.setAttribute('data-goto-page', nextPage.id);
    }

    function switchTab(tabId, anchorId) {
      state.activeTab = tabId;

      document.querySelectorAll('.nav-tab-btn').forEach(btn => {
        const isCurrent = btn.getAttribute('data-tab') === tabId;
        if (isCurrent) {
          btn.className = 'nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-semibold transition-all flex items-center gap-1.5 bg-orange-600 text-white';
        } else {
          btn.className = 'nav-tab-btn shrink-0 px-3 py-1.5 rounded-lg text-xs sm:text-sm font-medium transition-all flex items-center gap-1.5 text-slate-700 dark:text-slate-300 hover:bg-orange-50 dark:hover:bg-slate-800';
        }
      });

      document.querySelectorAll('.toc-nav-link').forEach(link => {
        const linkTab = link.getAttribute('data-goto');
        const href = link.getAttribute('href') || '';
        const isActive = (linkTab === tabId && (!anchorId || href === '#' + anchorId) && (tabId !== 'start-here' || href === '#view-start-here' || href === '#' + anchorId));
        if (isActive) {
          link.className = 'toc-nav-link toc-link-active block px-3 py-2 rounded-lg transition';
        } else {
          link.className = 'toc-nav-link block px-3 py-2 rounded-lg text-slate-600 dark:text-slate-300 hover:bg-orange-50/70 dark:hover:bg-slate-800 transition';
        }
      });

      updatePaginationUI();

      if (state.docMode === 'full') {
        const targetEl = document.getElementById(anchorId || ('view-' + tabId));
        if (targetEl) {
          targetEl.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      } else {
        applyDocModeUI();
        if (anchorId) {
          const anchorEl = document.getElementById(anchorId);
          if (anchorEl) {
            anchorEl.scrollIntoView({ behavior: 'smooth', block: 'start' });
            return;
          }
        }
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    }

    // =========================================================================
    // RENDER FUNCTIONS FOR MODULES
    // =========================================================================
    function renderToolsDirectory() {
      const container = document.getElementById('toolsDirectoryGrid');
      const searchVal = (document.getElementById('toolSearchInput')?.value || '').toLowerCase();
      if (!container) return;

      const filtered = coreToolsData.filter(t => {
        const matchesCat = state.selectedToolCat === 'All' || t.category === state.selectedToolCat;
        const matchesSearch = !searchVal ||
          t.name.toLowerCase().includes(searchVal) ||
          t.whatItDoes.toLowerCase().includes(searchVal) ||
          t.bestFor.toLowerCase().includes(searchVal) ||
          t.category.toLowerCase().includes(searchVal);
        return matchesCat && matchesSearch;
      });

      container.innerHTML = filtered.map(t => {
        const isSaved = state.savedTools.includes(t.name);
        return `
          <div class="p-5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 flex flex-col justify-between">
            <div>
              <div class="flex items-center justify-between gap-2 mb-3">
                <span class="text-xs font-mono font-bold px-2.5 py-0.5 rounded bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300">${t.category}</span>
                <button type="button" data-toggle-tool="${t.name}" class="toggle-tool-btn text-xs font-semibold px-2.5 py-1 rounded-lg border ${isSaved ? 'bg-orange-600 text-white border-orange-600' : 'bg-white dark:bg-slate-900 text-slate-700 dark:text-slate-300 border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500'}">
                  ${isSaved ? '★ In My Stack' : '☆ Add to Stack'}
                </button>
              </div>
              <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mb-1.5">${t.name}</h3>
              <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mb-3">${t.whatItDoes}</p>
              <div class="p-3 rounded-lg bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 text-xs text-slate-700 dark:text-slate-200 mb-3">
                <strong class="text-emerald-700 dark:text-emerald-400 uppercase block mb-0.5">Best For:</strong>
                ${t.bestFor}
              </div>
            </div>
            <div class="pt-2.5 border-t border-[#E5E0D8] dark:border-slate-700 text-xs text-slate-500 dark:text-slate-400">
              <strong class="text-slate-800 dark:text-slate-200">Where to start:</strong> ${t.getStarted}
            </div>
          </div>
        `;
      }).join('');

      container.querySelectorAll('.toggle-tool-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const toolName = btn.getAttribute('data-toggle-tool');
          const idx = state.savedTools.indexOf(toolName);
          if (idx >= 0) {
            state.savedTools.splice(idx, 1);
            showToast(`Removed ${toolName} from My Stack`);
          } else {
            state.savedTools.push(toolName);
            showToast(`Added ${toolName} to My Stack`);
          }
          updateSavedStackUI();
          renderToolsDirectory();
        });
      });
    }

    function updateSavedStackUI() {
      const countEl = document.getElementById('savedStackCount');
      if (countEl) countEl.textContent = String(state.savedTools.length);
      const listEl = document.getElementById('savedStackList');
      if (!listEl) return;
      if (state.savedTools.length === 0) {
        listEl.innerHTML = `<p class="text-xs text-slate-500 p-3 bg-[#FAF8F5] dark:bg-slate-800 rounded-lg">No tools saved yet. Click "☆ Add to Stack" in Core AI Tools.</p>`;
        return;
      }
      listEl.innerHTML = state.savedTools.map(name => `
        <div class="flex items-center justify-between p-3 rounded-lg bg-[#FAF8F5] dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700">
          <span class="text-sm font-semibold text-slate-900 dark:text-white">${name}</span>
          <button type="button" data-remove-stack="${name}" class="text-xs font-semibold text-rose-600 hover:underline">Remove</button>
        </div>
      `).join('');

      listEl.querySelectorAll('[data-remove-stack]').forEach(btn => {
        btn.addEventListener('click', () => {
          const name = btn.getAttribute('data-remove-stack');
          state.savedTools = state.savedTools.filter(item => item !== name);
          updateSavedStackUI();
          renderToolsDirectory();
        });
      });
    }

    function renderPromptsLibrary() {
      const container = document.getElementById('promptsLibraryGrid');
      if (!container) return;

      const topic = document.getElementById('varTopic')?.value || '[Topic]';
      const audience = document.getElementById('varAudience')?.value || '[Audience]';
      const tone = document.getElementById('varTone')?.value || '[Tone]';

      const filtered = promptsData.filter(p => state.selectedPromptCat === 'All' || p.category === state.selectedPromptCat);

      container.innerHTML = filtered.map(p => {
        const resolvedText = p.template
          .replace(/\[Topic\]/g, topic)
          .replace(/\[Audience\]/g, audience)
          .replace(/\[Tone\]/g, tone);

        return `
          <div class="p-5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 flex flex-col justify-between">
            <div>
              <div class="flex items-center justify-between gap-2 mb-2">
                <span class="text-xs font-mono font-bold px-2.5 py-0.5 rounded bg-blue-100 text-blue-800 dark:bg-blue-950 dark:text-blue-300">${p.category}</span>
                <span class="text-[11px] font-medium text-slate-500">Copy-Paste Ready</span>
              </div>
              <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mb-1">${p.title}</h3>
              <p class="text-xs text-slate-600 dark:text-slate-300 mb-3">${p.useCase}</p>
              <pre class="whitespace-pre-wrap font-mono text-xs text-slate-800 dark:text-slate-200 bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-3.5 mb-4 leading-relaxed">${resolvedText}</pre>
            </div>
            <button type="button" data-copy-prompt="${encodeURIComponent(resolvedText)}" class="copy-prompt-btn w-full btn-primary-orange py-2.5 px-4 rounded-xl text-xs flex items-center justify-center gap-2">
              <span>📋 Copy Customized Prompt</span>
            </button>
          </div>
        `;
      }).join('');

      container.querySelectorAll('.copy-prompt-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const text = decodeURIComponent(btn.getAttribute('data-copy-prompt'));
          copyTextToClipboard(text, 'Prompt copied to clipboard!');
        });
      });
    }

    function renderCanvaTemplates() {
      const container = document.getElementById('canvaTemplatesGrid');
      if (!container) return;
      container.innerHTML = canvaTemplatesData.map(item => `
        <div class="p-5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between gap-2 mb-3">
              <span class="text-xs font-mono font-bold px-2.5 py-0.5 rounded bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300">${item.category}</span>
              <span class="text-xs font-mono text-slate-500">${item.format}</span>
            </div>
            <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mb-2">${item.title}</h3>
            <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mb-4">${item.description}</p>
            <div class="bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-3.5 mb-4">
              <p class="text-xs font-bold text-emerald-700 dark:text-emerald-400 uppercase mb-2">Slide / Layout Structure:</p>
              <ul class="space-y-1.5 text-xs text-slate-700 dark:text-slate-300">
                ${item.structure.map(s => `<li class="flex items-start gap-2"><span class="text-orange-600 font-bold">▸</span><span>${s}</span></li>`).join('')}
              </ul>
            </div>
          </div>
          <button type="button" data-copy-canva="${encodeURIComponent(item.title + '\nFormat: ' + item.format + '\n\nStructure:\n- ' + item.structure.join('\n- '))}" class="copy-canva-btn w-full btn-secondary-doc py-2.5 px-4 rounded-xl text-xs">
            📋 Copy Slide Blueprint for Canva / Notion
          </button>
        </div>
      `).join('');

      container.querySelectorAll('.copy-canva-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const text = decodeURIComponent(btn.getAttribute('data-copy-canva'));
          copyTextToClipboard(text, 'Canva template blueprint copied!');
        });
      });
    }

    function renderCapcutTemplates() {
      const container = document.getElementById('capcutTemplatesGrid');
      if (!container) return;
      container.innerHTML = capcutTemplatesData.map(item => `
        <div class="p-5 rounded-xl bg-[#FAF8F5] dark:bg-slate-800/90 border border-[#E5E0D8] dark:border-slate-700 flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between gap-2 mb-3">
              <span class="text-xs font-mono font-bold px-2.5 py-0.5 rounded bg-orange-100 text-orange-800 dark:bg-orange-950 dark:text-orange-300">${item.duration}</span>
              <span class="text-xs font-mono text-slate-500">${item.style}</span>
            </div>
            <h3 class="font-display text-lg font-bold text-slate-900 dark:text-white mb-2">${item.title}</h3>
            <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mb-4">${item.description}</p>
            <div class="bg-white dark:bg-slate-900 border border-[#E5E0D8] dark:border-slate-700 rounded-xl p-3.5 mb-4">
              <p class="text-xs font-bold text-orange-700 dark:text-orange-400 uppercase mb-2">Editing Beat Sheet &amp; Timing:</p>
              <ul class="space-y-1.5 text-xs text-slate-700 dark:text-slate-300">
                ${item.beats.map(b => `<li class="flex items-start gap-2"><span class="text-orange-600 font-bold">▸</span><span>${b}</span></li>`).join('')}
              </ul>
            </div>
          </div>
          <button type="button" data-copy-capcut="${encodeURIComponent(item.title + ' (' + item.duration + ')\n\nBeats:\n- ' + item.beats.join('\n- '))}" class="copy-capcut-btn w-full btn-secondary-doc py-2.5 px-4 rounded-xl text-xs">
            📋 Copy CapCut Beat Sheet to Notion
          </button>
        </div>
      `).join('');

      container.querySelectorAll('.copy-capcut-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const text = decodeURIComponent(btn.getAttribute('data-copy-capcut'));
          copyTextToClipboard(text, 'CapCut editing recipe copied!');
        });
      });
    }

    function renderActiveWorkflow() {
      const container = document.getElementById('activeWorkflowDetail');
      if (!container) return;
      const wf = workflowsDetailData[state.activeWorkflow] || workflowsDetailData['short-form'];

      container.innerHTML = `
        <div class="flex flex-wrap items-center justify-between gap-3 border-b border-[#E5E0D8] dark:border-slate-700 pb-4 mb-5">
          <div>
            <span class="text-xs font-mono font-bold uppercase text-orange-600 dark:text-orange-400">${wf.multiplier}</span>
            <h3 class="font-display text-xl font-bold text-slate-900 dark:text-white mt-0.5">${wf.title}</h3>
            <p class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 mt-1">${wf.subtitle}</p>
          </div>
          <button type="button" id="btnCopyActiveWorkflow" class="btn-primary-orange px-4 py-2 rounded-lg text-xs">
            📋 Copy Workflow Checklist for Notion
          </button>
        </div>
        <div class="space-y-2.5">
          ${wf.steps.map((s, i) => `
            <label class="flex items-start gap-3 p-3.5 rounded-xl bg-white dark:bg-slate-800 border border-[#E5E0D8] dark:border-slate-700 hover:border-orange-500 cursor-pointer">
              <input type="checkbox" ${i === 0 ? 'checked' : ''} class="mt-1 w-4 h-4 accent-emerald-600 rounded" />
              <span class="text-xs sm:text-sm text-slate-800 dark:text-slate-200">${s}</span>
            </label>
          `).join('')}
        </div>
      `;

      const copyBtn = document.getElementById('btnCopyActiveWorkflow');
      if (copyBtn) {
        copyBtn.addEventListener('click', () => {
          const md = `### ${wf.title}\n> ${wf.subtitle}\n\n` + wf.steps.map(s => `- [ ] ${s}`).join('\n');
          copyTextToClipboard(md, 'Workflow Notion checklist copied!');
        });
      }
    }

    // Live AEO Answer Block Word Counter
    function updateAeoWordCount() {
      const ans = (document.getElementById('aeoDirectAnswer')?.value || '').trim();
      const words = ans ? ans.split(/\s+/).length : 0;
      const badge = document.getElementById('aeoWordCountBadge');
      if (!badge) return;
      if (words >= 35 && words <= 65) {
        badge.textContent = `${words} words • ✓ Optimal 40–60w AEO Sweet Spot`;
        badge.className = 'text-xs font-mono font-bold px-2.5 py-1 rounded-lg bg-emerald-100 text-emerald-800 dark:bg-emerald-950 dark:text-emerald-300';
      } else {
        badge.textContent = `${words} words • Aim for 40–60 words for AI citation`;
        badge.className = 'text-xs font-mono font-bold px-2.5 py-1 rounded-lg bg-amber-100 text-amber-800 dark:bg-amber-950 dark:text-amber-300';
      }
    }

    // =========================================================================
    // CHARTS INITIALIZATION (WARM EDITORIAL PALETTE: TANGERINE #F97316 & SAGE #16A34A)
    // =========================================================================
    let heroChartInstance = null;

    function initCharts() {
      if (typeof Chart === 'undefined') return;

      Chart.defaults.color = '#64748B';
      Chart.defaults.font.family = "'Inter', sans-serif";

      // 1. Hero Velocity Chart
      const heroCtx = document.getElementById('heroVelocityChart');
      if (heroCtx) {
        heroChartInstance = new Chart(heroCtx, {
          type: 'bar',
          data: {
            labels: ['01 Research', '02 Create', '03 Design', '04 Produce', '05 Publish', '06 Improve'],
            datasets: [
              {
                type: 'line',
                label: 'Repeatable Quality Index',
                data: [40, 58, 72, 85, 94, 100],
                borderColor: '#16A34A',
                backgroundColor: 'rgba(22, 163, 74, 0.12)',
                borderWidth: 2.5,
                pointBackgroundColor: '#16A34A',
                pointRadius: 4,
                tension: 0.35
              },
              {
                type: 'bar',
                label: 'Toolkit Workflow Velocity',
                data: [32, 50, 66, 78, 90, 96],
                backgroundColor: 'rgba(249, 115, 22, 0.82)',
                borderColor: '#EA580C',
                borderWidth: 1,
                borderRadius: 6
              }
            ]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
              legend: { display: true, labels: { boxWidth: 12, font: { size: 11 } } }
            },
            scales: {
              x: { grid: { color: 'rgba(148, 163, 184, 0.15)' } },
              y: { beginAtZero: true, grid: { color: 'rgba(148, 163, 184, 0.15)' } }
            }
          }
        });
      }

      // 2. Core AI Tools Radar Chart
      const radarCtx = document.getElementById('toolsRadarChart');
      if (radarCtx) {
        new Chart(radarCtx, {
          type: 'radar',
          data: {
            labels: ['Research Clarity', 'Draft Speed', 'Visual Polish', 'Video Pacing', 'SEO/AEO Structure'],
            datasets: [
              {
                label: 'Connected Toolkit Stack',
                data: [92, 94, 88, 90, 95],
                backgroundColor: 'rgba(249, 115, 22, 0.2)',
                borderColor: '#EA580C',
                pointBackgroundColor: '#EA580C',
                borderWidth: 2
              },
              {
                label: 'Ad-Hoc Manual Process',
                data: [45, 40, 52, 44, 38],
                backgroundColor: 'rgba(100, 116, 139, 0.12)',
                borderColor: '#64748B',
                pointBackgroundColor: '#64748B',
                borderWidth: 1.5
              }
            ]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            scales: {
              r: {
                ticks: { display: false, beginAtZero: true, max: 100 }
              }
            },
            plugins: {
              legend: { labels: { font: { size: 10 } } }
            }
          }
        });
      }

      // 3. CapCut Short-Form Retention Curve Chart
      const capcutCtx = document.getElementById('capcutRetentionChart');
      if (capcutCtx) {
        new Chart(capcutCtx, {
          type: 'line',
          data: {
            labels: ['0s Hook', '3s Hold', '10s Context', '20s Step 1', '30s Step 2', '40s Step 3', '45s CTA'],
            datasets: [
              {
                label: 'CapCut Template Recipe (% Viewer Retention)',
                data: [100, 78, 71, 66, 62, 59, 56],
                borderColor: '#EA580C',
                backgroundColor: 'rgba(249, 115, 22, 0.14)',
                fill: true,
                tension: 0.35,
                borderWidth: 2.5
              },
              {
                label: 'Unstructured Video (% Retention)',
                data: [100, 44, 32, 24, 19, 15, 12],
                borderColor: '#94A3B8',
                borderDash: [5, 5],
                fill: false,
                tension: 0.35,
                borderWidth: 2
              }
            ]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            scales: {
              x: { grid: { color: 'rgba(148, 163, 184, 0.15)' } },
              y: { beginAtZero: true, max: 100, grid: { color: 'rgba(148, 163, 184, 0.15)' } }
            }
          }
        });
      }

      // 4. SEO & AEO Signal Chart
      const seoCtx = document.getElementById('seoAeoChart');
      if (seoCtx) {
        new Chart(seoCtx, {
          type: 'bar',
          data: {
            labels: ['40–60w Answer Lead', 'Question H2/H3s', 'Original Creator Proof', 'Claim Verification'],
            datasets: [
              {
                label: 'SEO Ranking Weight',
                data: [78, 92, 85, 80],
                backgroundColor: 'rgba(249, 115, 22, 0.85)',
                borderRadius: 6
              },
              {
                label: 'AEO Citation Weight',
                data: [96, 91, 90, 94],
                backgroundColor: 'rgba(22, 163, 74, 0.82)',
                borderRadius: 6
              }
            ]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            scales: {
              x: { grid: { color: 'rgba(148, 163, 184, 0.15)' } },
              y: { beginAtZero: true, max: 100, grid: { color: 'rgba(148, 163, 184, 0.15)' } }
            }
          }
        });
      }
    }

    // =========================================================================
    // EVENT LISTENERS & INITIALIZATION
    // =========================================================================
    window.addEventListener('DOMContentLoaded', () => {
      renderToolsDirectory();
      renderPromptsLibrary();
      renderCanvaTemplates();
      renderCapcutTemplates();
      renderActiveWorkflow();
      updateSavedStackUI();
      updateAeoWordCount();
      applyDocModeUI();
      initCharts();

      // View Mode Switcher (Full Notion Doc vs Tabbed Focus)
      document.getElementById('btnModeFullDoc')?.addEventListener('click', () => {
        state.docMode = 'full';
        applyDocModeUI();
        showToast('Showing full scrollable Notion Doc');
      });

      document.getElementById('btnModeTabbed')?.addEventListener('click', () => {
        state.docMode = 'tabbed';
        applyDocModeUI();
        showToast('Switched to single-module Focus Tab View');
      });

      // Theme Toggle (Warm Paper Light vs Dark Slate)
      document.getElementById('btnToggleTheme')?.addEventListener('click', () => {
        document.documentElement.classList.toggle('dark');
        const isDark = document.documentElement.classList.contains('dark');
        showToast(isDark ? 'Switched to Dark Slate reading mode' : 'Switched to Warm Paper Notion mode');
      });

      // Top Nav Tab Clicks
      document.querySelectorAll('.nav-tab-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          switchTab(btn.getAttribute('data-tab'));
        });
      });

      // Brand Logo Home Click
      document.getElementById('brandHomeTrigger')?.addEventListener('click', () => {
        switchTab('start-here');
      });

      // All Quick Nav Buttons & Sidebar Links (data-goto)
      document.querySelectorAll('[data-goto]').forEach(btn => {
        btn.addEventListener('click', (e) => {
          const target = btn.getAttribute('data-goto');
          const href = btn.getAttribute('href');
          if (href && href.startsWith('#')) {
            e.preventDefault();
            const anchorId = href.slice(1);
            switchTab(target || 'start-here', anchorId);
          } else if (target) {
            switchTab(target);
          }
        });
      });

      document.getElementById('btnPrevPage')?.addEventListener('click', (e) => {
        const target = e.currentTarget.getAttribute('data-goto-page');
        if (target) switchTab(target);
      });
      document.getElementById('btnNextPage')?.addEventListener('click', (e) => {
        const target = e.currentTarget.getAttribute('data-goto-page');
        if (target) switchTab(target);
      });
      updatePaginationUI();

      // Hero Chart Mode Switcher
      const btnOutput = document.getElementById('btnHeroChartOutput');
      const btnTime = document.getElementById('btnHeroChartTime');
      const heroTitle = document.getElementById('heroChartTitle');

      btnOutput?.addEventListener('click', () => {
        btnOutput.className = 'px-3 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white transition';
        btnTime.className = 'px-3 py-1.5 rounded-lg text-xs font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition';
        if (heroTitle) heroTitle.textContent = 'Weekly Publishable Assets (Manual vs. Toolkit System)';
        if (heroChartInstance) {
          heroChartInstance.data.datasets[0].data = [40, 58, 72, 85, 94, 100];
          heroChartInstance.data.datasets[1].data = [32, 50, 66, 78, 90, 96];
          heroChartInstance.update();
        }
      });

      btnTime?.addEventListener('click', () => {
        btnTime.className = 'px-3 py-1.5 rounded-lg text-xs font-semibold bg-emerald-700 text-white transition';
        btnOutput.className = 'px-3 py-1.5 rounded-lg text-xs font-medium text-slate-600 dark:text-slate-300 hover:text-slate-900 transition';
        if (heroTitle) heroTitle.textContent = 'Hours Saved Per Week Across Each Workflow Stage';
        if (heroChartInstance) {
          heroChartInstance.data.datasets[0].data = [2.5, 4.0, 3.5, 5.0, 2.0, 3.0];
          heroChartInstance.data.datasets[1].data = [2.2, 3.8, 3.2, 4.6, 1.8, 2.8];
          heroChartInstance.update();
        }
      });

      // 6-Step Workflow Interactive Cards & Checkboxes
      function updateWorkflowProgressCount() {
        const checked = document.querySelectorAll('.step-checkbox:checked').length;
        const progEl = document.getElementById('headerWorkflowProgress');
        if (progEl) progEl.textContent = `${checked}/6 Steps`;
      }

      document.querySelectorAll('.workflow-step-card').forEach(card => {
        card.addEventListener('click', (e) => {
          const stepNum = Number(card.getAttribute('data-step'));
          if (e.target.tagName !== 'INPUT') {
            const cb = card.querySelector('.step-checkbox');
            if (cb) cb.checked = !cb.checked;
          }
          const cb = card.querySelector('.step-checkbox');
          if (cb && cb.checked) {
            card.classList.add('border-2', 'border-emerald-600');
          } else {
            card.classList.remove('border-2', 'border-emerald-600');
          }
          updateWorkflowProgressCount();

          const rec = stepRecommendations[stepNum];
          if (rec) {
            document.getElementById('inspectorStepBadge').textContent = rec.badge;
            document.getElementById('inspectorStepRecommendation').textContent = rec.text;
            const inspBtn = document.getElementById('inspectorStepBtn');
            if (inspBtn) {
              inspBtn.setAttribute('data-goto', rec.target);
              inspBtn.textContent = rec.btnText;
            }
          }
        });
      });

      document.getElementById('btnResetWorkflowSteps')?.addEventListener('click', () => {
        document.querySelectorAll('.step-checkbox').forEach(cb => {
          cb.checked = false;
        });
        document.querySelectorAll('.workflow-step-card').forEach(card => {
          card.classList.remove('border-2', 'border-emerald-600');
        });
        updateWorkflowProgressCount();
        showToast('Workflow step tracker reset!');
      });

      // Featured Workflows preview click
      document.querySelectorAll('.workflow-preview-item').forEach(item => {
        item.addEventListener('click', () => {
          const wfKey = item.getAttribute('data-workflow-select');
          if (wfKey) {
            state.activeWorkflow = wfKey;
            renderActiveWorkflow();
            switchTab('workflows');
          }
        });
      });

      // Workflow Tab Selector in Workflows View
      document.querySelectorAll('.wf-selector-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          state.activeWorkflow = btn.getAttribute('data-wf-tab');
          document.querySelectorAll('.wf-selector-btn').forEach(b => {
            b.className = 'wf-selector-btn text-left p-4 rounded-xl border border-[#E5E0D8] dark:border-slate-700 bg-[#FAF8F5] dark:bg-slate-800 hover:border-orange-500 transition';
          });
          btn.className = 'wf-selector-btn text-left p-4 rounded-xl border-2 border-orange-600 bg-orange-50/70 dark:bg-orange-950/30 transition';
          renderActiveWorkflow();
        });
      });

      // Tool Category Filters & Search
      document.querySelectorAll('.tool-cat-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          state.selectedToolCat = btn.getAttribute('data-tool-cat');
          document.querySelectorAll('.tool-cat-btn').forEach(b => {
            b.className = 'tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700';
          });
          btn.className = 'tool-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white';
          renderToolsDirectory();
        });
      });

      document.getElementById('toolSearchInput')?.addEventListener('input', () => {
        renderToolsDirectory();
      });

      // Prompt Category Filters & Live Variables
      document.querySelectorAll('.prompt-cat-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          state.selectedPromptCat = btn.getAttribute('data-prompt-cat');
          document.querySelectorAll('.prompt-cat-btn').forEach(b => {
            b.className = 'prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-medium bg-[#FAF8F5] dark:bg-slate-800 text-slate-700 dark:text-slate-300 border border-[#E5E0D8] dark:border-slate-700';
          });
          btn.className = 'prompt-cat-btn px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-orange-600 text-white';
          renderPromptsLibrary();
        });
      });

      document.querySelectorAll('.prompt-var-input').forEach(inp => {
        inp.addEventListener('input', () => {
          renderPromptsLibrary();
        });
      });

      document.getElementById('btnResetPromptVars')?.addEventListener('click', () => {
        document.getElementById('varTopic').value = 'AI Content Workflows for Solopreneurs';
        document.getElementById('varAudience').value = 'busy creators and small marketing teams';
        document.getElementById('varTone').value = 'practical, clear, zero-fluff, encouraging';
        renderPromptsLibrary();
        showToast('Prompt variables reset to defaults!');
      });

      // Canva Brand Hex Copy Buttons
      document.querySelectorAll('.hex-copy-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          const hex = btn.getAttribute('data-copy-hex');
          copyTextToClipboard(hex, `Copied ${hex} to clipboard!`);
        });
      });

      // AEO Answer Block Live Input & Copy
      document.getElementById('aeoDirectAnswer')?.addEventListener('input', updateAeoWordCount);

      document.getElementById('btnCopyAeoBlock')?.addEventListener('click', () => {
        const q = document.getElementById('aeoQuestion')?.value || '';
        const ans = document.getElementById('aeoDirectAnswer')?.value || '';
        const proof = document.getElementById('aeoProof')?.value || '';
        const md = `## ${q}\n\n**Direct Answer:** ${ans}\n\n> 💡 **Creator Insight (@ander.creative):** ${proof}`;
        copyTextToClipboard(md, 'AEO Answer Block copied for Notion!');
      });

      // Early Access Form Submit
      document.getElementById('earlyAccessForm')?.addEventListener('submit', (e) => {
        e.preventDefault();
        const email = document.getElementById('earlyAccessEmail')?.value || '';
        const focus = document.getElementById('earlyAccessFocus')?.value || '';
        const feedback = document.getElementById('earlyAccessFeedback');
        if (feedback) {
          feedback.textContent = `✓ Registered ${email} for early access (${focus})!`;
          feedback.classList.remove('hidden');
        }
        showToast('You are on the Ander Creative Early-Access List!');
      });

      // Modals (My Stack & Notion Embed Guide)
      const modalStack = document.getElementById('modalSavedStack');
      const modalNotion = document.getElementById('modalNotionGuide');

      document.getElementById('btnSavedStack')?.addEventListener('click', () => {
        modalStack?.classList.remove('hidden');
      });
      document.getElementById('closeSavedStack')?.addEventListener('click', () => {
        modalStack?.classList.add('hidden');
      });
      document.getElementById('btnCopyStackMarkdown')?.addEventListener('click', () => {
        const md = `### ★ My @ander.creative AI Tool Stack\n` + state.savedTools.map(t => `- [x] **${t}**`).join('\n');
        copyTextToClipboard(md, 'Saved Tool Stack copied as Notion Markdown!');
      });

      document.getElementById('btnNotionCodeModal')?.addEventListener('click', () => {
        modalNotion?.classList.remove('hidden');
      });
      document.getElementById('closeNotionGuide')?.addEventListener('click', () => {
        modalNotion?.classList.add('hidden');
      });

      document.getElementById('btnCopyNotionMarkdown')?.addEventListener('click', () => {
        const notionMd = `# ⚡ AI Creative & Marketing Toolkit (@ander.creative)
> **Start Here:** Welcome to your practical resource hub for AI-powered content creation and marketing.
> **The goal:** spend less time staring at a blank page and more time creating content that serves your audience.

## Explore the Toolkit
- **01 — Core AI Tools:** Discover AI tools for research, writing, design, video, and marketing. *Start here if: You're not sure which tool to use.*
- **02 — Copy-Paste AI Prompts:** Use practical prompts to brainstorm ideas, write social media posts, develop video scripts, improve marketing copy, and repurpose content. *Start here if: You know what you need to create but aren't sure how to prompt AI.*
- **03 — Canva Template Library:** Find customizable starting points for social media graphics, educational carousels, content calendars, lead magnets, and other marketing assets. *Start here if: You want to create polished visuals without designing everything from scratch.*
- **04 — CapCut Template Library:** Explore repeatable short-form video formats, editing recipes, caption styles, and production ideas for TikTok, Instagram Reels, and other vertical video platforms. *Start here if: You want to create videos faster and more consistently.*

## The Content Creation Workflow
- [ ] **01. Research** — Identify a real question, problem, or need your audience has.
- [ ] **02. Create** — Use an AI prompt to develop the idea, outline, script, or first draft.
- [ ] **03. Design** — Choose a Canva template or establish the visual direction.
- [ ] **04. Produce** — Edit your video or finalize your creative asset.
- [ ] **05. Publish** — Adapt the content to the platform and give your audience a clear next step.
- [ ] **06. Improve** — Review performance, learn from feedback, and refine the next version.

*Created by @ander.creative. Built to help you go from idea to execution.*`;
        copyTextToClipboard(notionMd, 'Complete Notion Markdown template copied!');
      });
    });
  </script>
</body>
</html>
