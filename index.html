import { useEffect, useMemo, useState } from "react";
import { createFileRoute } from "@tanstack/react-router";
import { ArrowRight, ArrowUpRight, Check, Clock3, Instagram, LockKeyhole, MessageCircle, Plus, Settings2, Sparkles, Trash2, Upload, X } from "lucide-react";
import { PhotoEditControl } from "@/components/photo-edit-control";

export const Route = createFileRoute("/")({
  head: () => ({ meta: [{ title: "Mica Lash | Realce sua beleza" }, { name: "description", content: "Agende seu horário na Mica Lash em Guarulhos." }, { property: "og:title", content: "Mica Lash | Realce sua beleza" }, { property: "og:description", content: "Agende seu horário na Mica Lash em Guarulhos." }, { property: "og:type", content: "website" }, { name: "twitter:card", content: "summary_large_image" }] }),
  component: Home,
});

type Service = { id: number; name: string; description: string; price: string; maintenancePrice: string; duration: string; image: string; };
type SitePhotos = { hero: string; about: string; logo: string; results: string[] };
const fallbackImage = "/lash-placeholder.svg";
const defaultLogo = "https://i.postimg.cc/sg0dMv3z/396621478-1431046954421962-93290028102472699-n.jpg";
const defaultSitePhotos: SitePhotos = { hero: fallbackImage, about: fallbackImage, logo: defaultLogo, results: [fallbackImage, fallbackImage, fallbackImage, fallbackImage] };
const initialServices: Service[] = [
  { id: 1, name: "Volume Brasileiro", description: "Fios tecnológicos para um olhar marcante, com leveza e definição.", price: "120", maintenancePrice: "", duration: "1h30", image: fallbackImage },
  { id: 2, name: "Volume Egípcio", description: "Textura sofisticada e preenchimento na medida certa.", price: "140", maintenancePrice: "", duration: "1h45", image: fallbackImage },
  { id: 3, name: "Volumão Brasileiro", description: "Mais intensidade e presença para valorizar seu olhar.", price: "150", maintenancePrice: "", duration: "2h", image: fallbackImage },
  { id: 4, name: "Mega Brasileiro", description: "Um efeito poderoso, com acabamento delicado e personalizado.", price: "170", maintenancePrice: "", duration: "2h", image: fallbackImage },
];
const gallery = [fallbackImage, fallbackImage, fallbackImage, fallbackImage];
const studioPhone = "5511991546233";
const studioAddress = "Av. Odair Santanelli, 800 - Parque Cecap, Guarulhos - SP";
const wa = (message: string) => "https://wa.me/" + studioPhone + "?text=" + encodeURIComponent(message);
const mapsDirections = (address: string) => "https://www.google.com/maps/dir/?api=1&destination=" + encodeURIComponent(address || studioAddress);

function Home() {
  const [services, setServices] = useState<Service[]>(initialServices);
  const [brand, setBrand] = useState("Mica Lash");
  const [instagram, setInstagram] = useState("@micalashs");
  const [location, setLocation] = useState(studioAddress);
  const [bio, setBio] = useState("Realçando sua beleza e elevando sua autoestima, um olhar de cada vez.");
  const [selected, setSelected] = useState<number | null>(null);
  const [date, setDate] = useState("");
  const [time, setTime] = useState("09:00");
  const [customer, setCustomer] = useState("");
  const [phone, setPhone] = useState("");
  const [bookingOpen, setBookingOpen] = useState(false);
  const [adminOpen, setAdminOpen] = useState(false);
  const [inlineEditMode, setInlineEditMode] = useState(false);
  const [loginOpen, setLoginOpen] = useState(false);
  const [password, setPassword] = useState("");
  const [logged, setLogged] = useState(false);
  const [tab, setTab] = useState<"services" | "photos" | "brand">("services");
  const [sitePhotos, setSitePhotos] = useState<SitePhotos>(defaultSitePhotos);
  const [editing, setEditing] = useState<Service | null>(null);
  const [toast, setToast] = useState("");

  useEffect(() => {
    try {
      const saved = localStorage.getItem("mica-lash-preview");
      if (saved) {
        const data = JSON.parse(saved);
        setServices(data.services || initialServices); setSitePhotos({...defaultSitePhotos,...data.sitePhotos,results:data.sitePhotos?.results || defaultSitePhotos.results}); setBrand(data.brand || "Mica Lash");
        setInstagram(!data.instagram || data.instagram === "@micaelly.barross" ? "@micalashs" : data.instagram); setLocation(data.location && data.location !== "Cecap, Guarulhos • SP" ? data.location : studioAddress); setBio(data.bio || "Realçando sua beleza e elevando sua autoestima, um olhar de cada vez.");
      }
    } catch { /* preview starts with sample content */ }
  }, []);
  const save = (next?: Partial<{services: Service[]; brand: string; instagram: string; location: string; bio: string; sitePhotos: SitePhotos}>) => {
    const data = { services, brand, instagram, location, bio, sitePhotos, ...next };
    localStorage.setItem("mica-lash-preview", JSON.stringify(data));
    setToast("Alterações salvas neste dispositivo"); setTimeout(() => setToast(""), 2600);
  };
  const chosen = useMemo(() => services.find(s => s.id === selected), [services, selected]);
  const openAdmin = () => { if (logged) setAdminOpen(true); else setLoginOpen(true); };
  const login = () => { if (password === "1234") { setLogged(true); setLoginOpen(false); setAdminOpen(true); setPassword(""); } else setToast("Senha incorreta"); };
  const sendBooking = () => {
    if (!chosen || !customer.trim() || !date) return;
    const msg = `Olá, Mica! Quero solicitar um agendamento 💜\nNome: ${customer}\nTelefone: ${phone || "Não informado"}\nServiço: ${chosen.name}\nValor: R$ ${chosen.price}\nManutenção: ${chosen.maintenancePrice ? "R$ " + chosen.maintenancePrice : "a combinar"}\nData: ${date}\nHorário desejado: ${time}\nValor: R$ ${chosen.price}`;
    window.open(wa(msg), "_blank", "noopener,noreferrer");
    setBookingOpen(false);
  };
  const saveService = () => {
    if (!editing || !editing.name.trim()) return;
    const next = services.some(s => s.id === editing.id) ? services.map(s => s.id === editing.id ? editing : s) : [...services, editing];
    setServices(next); save({services: next}); setEditing(null);
  };
  const uploadSitePhoto = (key: "hero" | "about" | "logo" | "results", file?: File, index?: number) => {
    if (!file) return;
    const reader = new FileReader();
    reader.onload = () => {
      const img = new Image();
      img.onload = () => {
        const max = key === "logo" ? 700 : 1400;
        const scale = Math.min(1, max / img.width);
        const canvas = document.createElement("canvas");
        canvas.width = Math.round(img.width * scale); canvas.height = Math.round(img.height * scale);
        const ctx = canvas.getContext("2d"); if (!ctx) return;
        ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
        const value = canvas.toDataURL("image/jpeg", 0.78);
        const next: SitePhotos = {...sitePhotos, results:[...sitePhotos.results]};
        if (key === "results" && typeof index === "number") next.results[index] = value;
        else if (key !== "results") next[key] = value;
        setSitePhotos(next); save({sitePhotos:next});
      };
      img.src = String(reader.result);
    };
    reader.readAsDataURL(file);
  };
  const uploadServicePhoto = (id: number, file?: File) => {
    if (!file) return;
    const reader = new FileReader();
    reader.onload = () => {
      const img = new Image();
      img.onload = () => {
        const scale = Math.min(1, 1200 / img.width);
        const canvas = document.createElement("canvas");
        canvas.width = Math.round(img.width * scale); canvas.height = Math.round(img.height * scale);
        const ctx = canvas.getContext("2d"); if (!ctx) return;
        ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
        const next = services.map(item => item.id === id ? {...item, image: canvas.toDataURL("image/jpeg", 0.78)} : item);
        setServices(next); save({services:next});
      };
      img.src = String(reader.result);
    };
    reader.readAsDataURL(file);
  };
  const inlinePhotoEditor = (key: "hero" | "about" | "logo" | "results", index?: number) => logged && inlineEditMode ? <PhotoEditControl className="inline-photo-edit" size={14} label=" Alterar foto" onUpload={file => uploadSitePhoto(key, file, index)} /> : null;
  const uploadImage = (file?: File) => {
    if (!file || !editing) return;
    const reader = new FileReader(); reader.onload = () => { const img = new Image(); img.onload = () => { const scale = Math.min(1, 1200 / img.width); const canvas = document.createElement("canvas"); canvas.width = Math.round(img.width * scale); canvas.height = Math.round(img.height * scale); const ctx = canvas.getContext("2d"); if (!ctx) return; ctx.drawImage(img, 0, 0, canvas.width, canvas.height); setEditing({...editing, image: canvas.toDataURL("image/jpeg", 0.78)}); }; img.src = String(reader.result); }; reader.readAsDataURL(file);
  };

  return <main className="mica-page">
    <div className="announcement"><Sparkles size={14}/> SEU MOMENTO DE SE CUIDAR COMEÇA AQUI <Sparkles size={14}/></div>{logged && inlineEditMode && <div className="inline-edit-toolbar"><span><Check size={15}/> Modo de edição ativado</span><small>Toque em qualquer foto marcada para trocar.</small><button onClick={()=>setInlineEditMode(false)}>Concluir edição <X size={14}/></button></div>}
    <header className="site-header">
      <a className="brand" href="#inicio"><span className="logo-image-wrap"><img className="original-logo" src={sitePhotos.logo || defaultLogo} alt="Logo original Mica Lash"/>{inlinePhotoEditor("logo")}</span><span><b>{brand}</b><small>BEAUTY STUDIO</small></span></a>
      <nav><a className="nav-book" href="#agendamento">Agendar</a><a href="#servicos">Serviços</a><a href="#sobre">Sobre mim</a><a href="#galeria">Resultados</a><a href="#como-chegar">Como chegar</a><a href="#faq">Perguntas frequentes</a></nav>
      <a className="header-instagram" href={`https://www.instagram.com/${instagram.replace("@","")}/`} target="_blank" rel="noreferrer"><Instagram size={22}/></a>
      <a className="contact-pill" href={wa("Olá, Mica! Gostaria de tirar uma dúvida 💜")} target="_blank" rel="noreferrer"><MessageCircle size={15}/> <span>Fale comigo</span></a>
    </header>

    <section className="hero" id="inicio">
      <div className="hero-copy">
        <div className="eyebrow"><span/> LASH DESIGNER • GUARULHOS, SP</div>
        <h1>{brand}</h1><div className="hero-script">Realce o que há de mais lindo em você 💜</div>
        <p>{bio}</p><div className="hero-benefits"><span>✧ Alongamento de cílios</span><span>♡ Beleza e autoestima</span><span>♧ Atendimento personalizado</span></div>
        <div className="hero-actions"><button className="primary-btn" onClick={() => setBookingOpen(true)}>Agendar meu horário <ArrowRight size={17}/></button><a className="text-link" href="#servicos">Conhecer serviços <ArrowUpRight size={16}/></a></div>
        <div className="hero-proof"><div className="avatar-stack"><span>✦</span><span>♡</span><span>✧</span></div><div><b>Um olhar que transforma</b><small>Atendimento com carinho e cuidado em cada detalhe</small></div></div>
      </div>
      <div className="hero-visual redesign-visual"><div className="hero-image"><img src={sitePhotos.hero || fallbackImage} alt="Detalhe de cílios e maquiagem" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/>{inlinePhotoEditor("hero")}<div className="image-note"><span>01 / 04</span><b>Beleza em cada detalhe.</b></div></div><div className="round-stamp"><span>REALCE SUA</span><b>BELEZA</b><span>✦ DESDE SEMPRE ✦</span></div><div className="floating-heart">♡</div></div>
    </section>

    <section className="inline-booking" id="agendamento">
      <div className="inline-booking-heading"><div><span className="eyebrow">RESERVE SEU MOMENTO</span><h2>Seu próximo olhar começa <em>aqui.</em></h2></div><p>Escolha o procedimento, informe quando prefere e envie sua solicitação para a Mica.</p></div>
      <div className="inline-booking-grid">
        <div className="inline-book-services"><h3>1. Escolha seu serviço</h3>{services.map((item,i)=><button key={item.id} className={selected===item.id?"inline-service active":"inline-service"} onClick={()=>setSelected(item.id)}><span className="service-image-wrap"><img src={item.image || gallery[i%gallery.length]} alt="" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/>{logged && inlineEditMode && <PhotoEditControl className="service-inline-edit" size={12} onUpload={file => uploadServicePhoto(item.id, file)} />}</span><span><b>{item.name}</b><small>{item.description}</small><strong>A partir de R$ {Number(item.price).toLocaleString("pt-BR")}</strong><small className="maintenance-label">{item.maintenancePrice ? "Manutenção: R$ "+Number(item.maintenancePrice).toLocaleString("pt-BR") : "Manutenção: consultar"}</small></span><i>{selected===item.id?"✓":""}</i></button>)}</div>
        <div className="inline-book-details"><h3>2. Data e horário</h3><label>Data desejada<input type="date" min={new Date().toISOString().slice(0,10)} value={date} onChange={e=>setDate(e.target.value)}/></label><label>Horário preferido<select value={time} onChange={e=>setTime(e.target.value)}>{["09:00","09:30","10:00","10:30","11:00","11:30","13:00","13:30","14:00","14:30","15:00","15:30","16:00","16:30","17:00"].map(t=><option key={t}>{t}</option>)}</select></label><h3>3. Seus dados</h3><label>Seu nome<input value={customer} onChange={e=>setCustomer(e.target.value)} placeholder="Como podemos te chamar?"/></label><label>WhatsApp<input value={phone} onChange={e=>setPhone(e.target.value)} placeholder="(11) 99999-9999"/></label></div>
        <aside className="inline-summary"><div className="summary-check">✓</div><h3>Resumo do agendamento</h3>{chosen?<><img src={chosen.image} alt="" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/><b>{chosen.name}</b><strong>R$ {Number(chosen.price).toLocaleString("pt-BR")},00</strong></>:<p>Escolha um serviço para ver o resumo.</p>}<div className="summary-meta"><span>Data <b>{date?new Date(date+"T12:00:00").toLocaleDateString("pt-BR"):"A escolher"}</b></span><span>Horário <b>{time}</b></span></div><button className="primary-btn" disabled={!chosen||!date||!customer.trim()} onClick={sendBooking}>Confirmar agendamento <ArrowRight size={16}/></button><small><LockKeyhole size={12}/> Seus dados estão seguros</small></aside>
      </div>
    </section>

    <section className="ticker"><div>UM TEMPO PARA VOCÊ <span>✦</span> AUTOESTIMA EM PRIMEIRO LUGAR <span>✦</span> SEU OLHAR, SUA IDENTIDADE <span>✦</span> UM TEMPO PARA VOCÊ <span>✦</span></div></section>

    <section className="services section-wrap" id="servicos">
      <div className="section-heading"><div><div className="eyebrow"><span/> ESCOLHA SEU ESTILO</div><h2>Um efeito para<br/><em>cada versão sua.</em></h2></div><p>Realce sua beleza com técnicas pensadas para combinar com você. Escolha seu efeito favorito e reserve seu momento.</p></div>
      <div className="service-grid">{services.map((s, i) => <article className="service-card" key={s.id}><div className="service-photo"><img src={s.image || gallery[i % gallery.length]} alt={s.name} onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/><span className="service-number">0{i+1}</span><button aria-label={"Agendar "+s.name} onClick={() => {setSelected(s.id);setBookingOpen(true)}}><ArrowUpRight/></button></div><div className="service-info"><div><h3>{s.name}</h3><span className="duration"><Clock3 size={13}/>{s.duration}</span></div><p>{s.description}</p><div className="service-bottom"><b>R$ {Number(s.price || 0).toLocaleString("pt-BR")}</b><small className="service-maintenance">{s.maintenancePrice ? "Manutenção R$ "+Number(s.maintenancePrice).toLocaleString("pt-BR") : "Manutenção sob consulta"}</small><button onClick={() => {setSelected(s.id);setBookingOpen(true)}}>Agendar <ArrowRight size={14}/></button></div></div></article>)}</div>
      <div className="center-link"><span>Não sabe qual escolher?</span> <a href={wa("Olá! Gostaria de ajuda para escolher o melhor efeito de cílios.")} target="_blank" rel="noreferrer">Converse com a Mica <ArrowUpRight size={14}/></a></div>
    </section>

    <section className="about" id="sobre"><div className="about-image"><img src={sitePhotos.about || fallbackImage} alt="Momento de beleza" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/>{inlinePhotoEditor("about")}<div className="about-caption">CUIDADO • TÉCNICA • AUTOESTIMA</div></div><div className="about-copy"><div className="eyebrow"><span/> MUITO PRAZER, SOU A MICA</div><h2>Mais do que cílios.<br/><em>Um carinho em você.</em></h2><p>Meu propósito é valorizar a beleza que já existe em você. Cada atendimento é pensado com atenção aos detalhes, respeitando seu estilo e criando um resultado que faça você se sentir ainda mais confiante.</p><div className="signature">Com carinho, Mica <span>♡</span></div><a className="text-link" href="https://www.instagram.com/micalashs/" target="_blank" rel="noreferrer">Acompanhe meu trabalho <Instagram size={16}/></a></div></section>

    <section className="gallery section-wrap" id="galeria"><div className="section-heading"><div><div className="eyebrow"><span/> UM POUCO DO MEU TRABALHO</div><h2>Olhares que<br/><em>falam por si.</em></h2></div><a className="text-link" href={`https://instagram.com/${instagram.replace("@","")}`} target="_blank" rel="noreferrer">Ver Instagram <ArrowUpRight size={16}/></a></div><div className="gallery-grid">{sitePhotos.results.map((src,i)=><a href={src} target="_blank" rel="noreferrer" key={`${src}-${i}`}><img src={src} alt={`Resultado de extensão de cílios ${i+1}`} onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/><span>✦ MICA LASH</span>{inlinePhotoEditor("results",i)}</a>)}</div></section>

    <section className="directions-section" id="como-chegar"><div className="directions-copy"><span className="eyebrow">VISITE A MICA LASH</span><h2>Como <em>chegar</em></h2><p>{location || studioAddress}</p><a className="primary-btn" href={mapsDirections(location)} target="_blank" rel="noreferrer">Abrir rota no Google Maps <ArrowUpRight size={17}/></a><a className="directions-phone" href="tel:+5511991546233">Ligar: (11) 99154-6233</a><small>Agende seu horário pelo WhatsApp: (11) 99154-6233</small><div className="payment-note"><b>Formas de pagamento</b><p>Aceitamos dinheiro, Pix e cartões. No cartão há acréscimo da taxa da maquininha; dinheiro e Pix têm valor normal.</p></div></div><div className="map-frame"><iframe title="Localização da Mica Lash no Google Maps" src={"https://www.google.com/maps?q="+encodeURIComponent(location || studioAddress)+"&output=embed"} loading="lazy" referrerPolicy="no-referrer-when-downgrade" allowFullScreen/><a href={mapsDirections(location)} target="_blank" rel="noreferrer">Ver no Google Maps</a></div></section><section className="faq-strip" id="faq"><div><span className="eyebrow">PERGUNTAS FREQUENTES</span><h2>Ficou com alguma dúvida?</h2><p>Chame a Mica e receba orientação para escolher seu procedimento.</p></div><a href={wa("Olá, Mica! Tenho uma dúvida sobre os procedimentos.")} target="_blank" rel="noreferrer">Fale comigo <ArrowUpRight/></a></section>
    <section className="cta-band" id="contato"><div className="cta-flower">✳</div><div><div className="eyebrow">SEU PRÓXIMO MOMENTO FAVORITO</div><h2>Pronta para se apaixonar<br/>pelo seu olhar?</h2><p>Escolha seu procedimento e vamos encontrar o melhor horário para você.</p></div><button className="light-btn" onClick={() => setBookingOpen(true)}>Quero agendar <ArrowUpRight size={17}/></button></section>

    <footer className="footer"><div className="footer-top"><a className="brand footer-brand" href="#inicio"><span className="brand-mark">M<span>✦</span></span><span><b>{brand}</b><small>BEAUTY STUDIO</small></span></a><p>Realçando sua beleza, elevando sua autoestima.</p><div className="socials"><a href={`https://instagram.com/${instagram.replace("@","")}`} target="_blank" rel="noreferrer"><Instagram/></a><a href={wa("Olá, Mica! Gostaria de informações sobre agendamento.")} target="_blank" rel="noreferrer"><MessageCircle/></a></div></div><div className="footer-bottom"><span>© 2025 {brand}. Feito com carinho.</span><span>{location}</span><a href={mapsDirections(location)} target="_blank" rel="noreferrer">Como chegar</a><a href="tel:+5511991546233">(11) 99154-6233</a><button className="admin-trigger" onClick={openAdmin} aria-label="Acesso da lojista"><LockKeyhole size={12}/> Área da lojista</button></div></footer>

    {bookingOpen && <div className="modal-backdrop" onClick={() => setBookingOpen(false)}><div className="booking-modal" onClick={e => e.stopPropagation()}><button className="modal-close" onClick={() => setBookingOpen(false)}><X/></button><div className="eyebrow"><span/> RESERVE SEU MOMENTO</div><h2>Vamos agendar?</h2><p className="modal-intro">Preencha os dados e envie sua solicitação pelo WhatsApp.</p><label>Procedimento</label><div className="choice-list">{services.map(s=><button key={s.id} className={selected===s.id?"choice active":"choice"} onClick={()=>setSelected(s.id)}><span><b>{s.name}</b><small>{s.duration}</small></span><strong>R$ {Number(s.price).toLocaleString("pt-BR")}</strong><small>{s.maintenancePrice ? "Manutenção R$ "+s.maintenancePrice : "Manutenção a definir"}</small>{selected===s.id&&<Check size={16}/>}</button>)}</div><div className="form-row"><label>Seu nome<input value={customer} onChange={e=>setCustomer(e.target.value)} placeholder="Como podemos te chamar?"/></label><label>WhatsApp<input value={phone} onChange={e=>setPhone(e.target.value)} placeholder="(11) 99999-9999"/></label></div><div className="form-row"><label>Data desejada<input type="date" min={new Date().toISOString().slice(0,10)} value={date} onChange={e=>setDate(e.target.value)}/></label><label>Horário preferido<select value={time} onChange={e=>setTime(e.target.value)}>{["09:00","10:00","11:00","13:00","14:00","15:00","16:00","17:00"].map(t=><option key={t}>{t}</option>)}</select></label></div><button className="primary-btn full-btn" disabled={!chosen||!customer.trim()||!date} onClick={sendBooking}>Solicitar pelo WhatsApp <ArrowRight size={17}/></button><small className="fine-print">O horário será confirmado diretamente com a profissional.</small></div></div>}

    {loginOpen && <div className="modal-backdrop" onClick={()=>setLoginOpen(false)}><div className="login-modal" onClick={e=>e.stopPropagation()}><button className="modal-close" onClick={()=>setLoginOpen(false)}><X/></button><div className="login-icon"><LockKeyhole/></div><h2>Área da lojista</h2><p>Entre com sua senha para personalizar seu espaço.</p><input type="password" value={password} onChange={e=>setPassword(e.target.value)} onKeyDown={e=>e.key==="Enter"&&login()} placeholder="Digite sua senha"/><button className="primary-btn full-btn" onClick={login}>Acessar painel <ArrowRight size={16}/></button><small>Prévia demonstrativa • senha inicial 1234</small></div></div>}

    {adminOpen && <div className="admin-overlay"><aside className="admin-panel"><div className="admin-head"><div><span className="admin-kicker">MICA LASH • STUDIO</span><h2>Painel da lojista</h2></div><button className="inline-mode-launch" onClick={()=>{setAdminOpen(false);setInlineEditMode(true);}}>Editar direto no site <ArrowUpRight size={14}/></button><button className="icon-button" onClick={()=>setAdminOpen(false)}><X/></button></div><div className="admin-tabs"><button className={tab==="services"?"selected":""} onClick={()=>setTab("services")}><Sparkles size={15}/> Serviços</button><button className={tab==="photos"?"selected":""} onClick={()=>setTab("photos")}><Upload size={15}/> Fotos do site</button><button className={tab==="brand"?"selected":""} onClick={()=>setTab("brand")}><Settings2 size={15}/> Meu espaço</button></div>{tab==="services"?<div className="admin-content"><div className="admin-section-title"><div><h3>Seus procedimentos</h3><p>Edite o catálogo exibido no site.</p></div><button className="add-btn" onClick={()=>setEditing({id:Date.now(),name:"",description:"",price:"",duration:"1h30",maintenancePrice:"",image:fallbackImage})}><Plus size={16}/> Novo</button></div>{services.map(s=><div className="admin-service" key={s.id}><img src={s.image || fallbackImage} alt="" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/><div><b>{s.name}</b><small>Aplicação R$ {s.price} • Manutenção {s.maintenancePrice ? "R$ "+s.maintenancePrice : "a definir"} • {s.duration}</small></div><button onClick={()=>setEditing({...s})}><Settings2 size={16}/></button><button onClick={()=>{const next=services.filter(x=>x.id!==s.id);setServices(next);save({services:next})}}><Trash2 size={16}/></button></div>)}{editing&&<div className="edit-card"><div className="edit-title"><h3>{services.some(s=>s.id===editing.id)?"Editar procedimento":"Novo procedimento"}</h3><button onClick={()=>setEditing(null)}><X size={17}/></button></div><label>Nome<input value={editing.name} onChange={e=>setEditing({...editing,name:e.target.value})}/></label><label>Descrição<textarea value={editing.description} onChange={e=>setEditing({...editing,description:e.target.value})}/></label><div className="form-row"><label>Preço (R$)<input value={editing.price} onChange={e=>setEditing({...editing,price:e.target.value})}/></label><label>Duração<input value={editing.duration} onChange={e=>setEditing({...editing,duration:e.target.value})}/></label><label>Valor da manutenção (R$)<input inputMode="decimal" placeholder="Ex.: 80" value={editing.maintenancePrice || ""} onChange={e=>setEditing({...editing,maintenancePrice:e.target.value})}/></label></div><label className="upload-box"><Upload size={17}/> {editing.image?"Trocar foto do procedimento":"Enviar foto do procedimento"}<input type="file" accept="image/*" onChange={e=>uploadImage(e.target.files?.[0])}/></label>{editing.image&&<img className="edit-preview" src={editing.image} alt="Prévia" onError={(e) => { e.currentTarget.onerror = null; e.currentTarget.src = fallbackImage; }}/>}<button className="primary-btn full-btn" onClick={saveService}>Salvar procedimento <Check size={16}/></button></div>}</div>:tab==="photos"?<div className="admin-content photo-manager">
      <div className="photo-manager-intro"><span className="photo-manager-icon"><Sparkles size={18}/></span><h3>Fotos do seu site</h3><p>É simples: escolha uma área, toque em <b>Trocar foto</b> e selecione uma imagem do celular ou computador. A prévia aparece aqui automaticamente. Como esta é uma demonstração, as fotos ficam salvas somente neste navegador.</p></div>
      <div className="photo-upload-card"><img src={sitePhotos.hero || fallbackImage} alt="Prévia da capa"/><div><b>1. Foto principal (capa)</b><small>É a primeira imagem grande que aparece quando a cliente abre o site.</small><label className="photo-change-btn"><Upload size={15}/> Trocar foto<input type="file" accept="image/*" onChange={e=>uploadSitePhoto("hero",e.target.files?.[0])}/></label></div></div>
      <div className="photo-upload-card"><img src={sitePhotos.about || fallbackImage} alt="Prévia da seção sobre"/><div><b>2. Foto da seção “Sobre mim”</b><small>Uma foto sua ou do seu espaço para apresentar seu trabalho.</small><label className="photo-change-btn"><Upload size={15}/> Trocar foto<input type="file" accept="image/*" onChange={e=>uploadSitePhoto("about",e.target.files?.[0])}/></label></div></div>
      <div className="photo-upload-card"><img className="logo-photo-preview" src={sitePhotos.logo || defaultLogo} alt="Prévia da logo"/><div><b>3. Logo do estúdio</b><small>Aparece no topo do site, ao lado do nome Mica Lash.</small><label className="photo-change-btn"><Upload size={15}/> Trocar logo<input type="file" accept="image/*" onChange={e=>uploadSitePhoto("logo",e.target.files?.[0])}/></label></div></div>
      <div className="photo-results-heading"><h3>4. Fotos dos resultados</h3><p>Troque cada quadrinho por uma foto diferente dos seus trabalhos.</p></div>
      <div className="photo-results-grid">{sitePhotos.results.map((src,i)=><div className="photo-result-card" key={i}><img src={src || fallbackImage} alt={"Resultado "+(i+1)}/><b>Foto {i+1}</b><label className="photo-change-btn"><Upload size={14}/> Trocar<input type="file" accept="image/*" onChange={e=>uploadSitePhoto("results",e.target.files?.[0],i)}/></label></div>)}</div>
      <div className="photo-manager-tip"><LockKeyhole size={16}/><span><b>Dica para escolher as fotos</b><small>Prefira fotos bem iluminadas e próximas dos cílios. O site ajusta o enquadramento automaticamente.</small></span></div>
      <button className="photo-reset-btn" onClick={()=>{setSitePhotos(defaultSitePhotos);save({sitePhotos:defaultSitePhotos})}}>Restaurar fotos de exemplo</button>
      </div>:<div className="admin-content"><h3>Identidade do seu espaço</h3><p className="admin-help">Atualize as informações que aparecem para suas clientes.</p><label>Nome do studio<input value={brand} onChange={e=>setBrand(e.target.value)}/></label><label>Instagram<input value={instagram} onChange={e=>setInstagram(e.target.value)}/></label><label>Localização<input value={location} onChange={e=>setLocation(e.target.value)}/></label><label>Mensagem de apresentação<textarea value={bio} onChange={e=>setBio(e.target.value)}/></label><button className="primary-btn full-btn" onClick={()=>save()}>Salvar identidade <Check size={16}/></button><div className="demo-notice"><LockKeyhole size={16}/><span><b>Acesso demonstrativo</b><small>As alterações ficam salvas neste navegador. Para uso real em vários dispositivos, conecte um banco de dados e armazenamento de imagens.</small></span></div></div>}<div className="admin-foot"><span>Prévia personalizável</span><button onClick={()=>{setLogged(false);setAdminOpen(false)}}>Sair do painel</button></div></aside></div>}
    {toast&&<div className="toast"><Check size={16}/>{toast}</div>}
  </main>;
}
