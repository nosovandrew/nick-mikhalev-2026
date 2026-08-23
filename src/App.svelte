<script>
    const partnerImages = import.meta.glob(
        "./lib/assets/images/partners/*.png",
        {
            eager: true,
            import: "default",
            query: "?url",
        },
    );

    const partnerFiles = [
        "Logo_Mercedes.png",
        "Logo_Nissan.png",
        "Logo_Pepsi.png",
        "Logo_Suzuki.png",
        "Logo_Omoda.png",
        "Logo_Hyundai.png",
        "Logo_Zeekr.png",
        "Logo_Renault.png",
        "Logo_Mitsubishi.png",
        "Logo_Heineken.png",
        "Logo_Opel.png",
        "Logo_Iveco.png",
        "Logo_Peugeot.png",
        "Logo_Alfa_Romeo.png",
        "Logo_Jaecoo.png",
        "Logo_Toyota.png",
        "Logo_RAM.png",
        "Logo_Jeep.png",
        "Logo_MAN.png",
        "Logo_Evian.png",
        "Logo_Geely.png",
        "Logo_MG.png",
        "Logo_Infiniti.png",
        "Logo_Ferrari.png",
        "Logo_Citroen.png",
        "Logo_Chery.png",
        "Logo_BYD.png",
        "Logo_Fiat.png",
    ];

    const partners = partnerFiles.map((file) => ({
        name: file.replace(/^Logo_/, "").replace(/_/g, " ").replace(".png", ""),
        src: partnerImages[`./lib/assets/images/partners/${file}`],
    }));

    const contacts = [
        {
            label: "telegram",
            href: "https://t.me/velahim",
        },
        {
            label: "email",
            href: "mailto:nickmikhalev@gmail.com",
        },
    ];
</script>

<section class="container">
    <h1 class="visually-hidden">Nick Mikhalev</h1>
    <p class="container__hero">full-time with these clients...</p>
    <div class="container__partners">
        {#each partners as partner}
            <div class="container__partner">
                <img src={partner.src} alt={partner.name} />
            </div>
        {/each}
    </div>
    <footer class="container__contact">
        <p class="container__contact-text">let's work together</p>
        <ul class="container__contact-list" aria-label="Contacts">
            {#each contacts as contact}
                <li>
                    <a href={contact.href}>{contact.label}</a>
                </li>
            {/each}
        </ul>
    </footer>
</section>
