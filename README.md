# noorain-site
import { useState } from "react";

export default function ProductGrid() {
  const [searchTerm, setSearchTerm] = useState("");
  const [formData, setFormData] = useState({ name: "", email: "", message: "" });

  const handleFormChange = (e) => {
    const { name, value } = e.target;
    setFormData({ ...formData, [name]: value });
  };

  const handleFormSubmit = (e) => {
    e.preventDefault();
    const whatsappLink = `https://wa.me/7972530698?text=Reseller%20Inquiry%0AName:%20${formData.name}%0AEmail:%20${formData.email}%0AMessage:%20${formData.message}`;
    window.open(`mailto:nooraincosmetics@gmail.com?subject=Reseller Inquiry&body=Name: ${formData.name}%0AEmail: ${formData.email}%0AMessage: ${formData.message}`);
    window.open(whatsappLink);
  };

  const products = [
    {
      img: "/mnt/data/photo_2025-06-22_08-49-14.jpg",
      alt: "Brightening Night Cream",
      title: "Noorain Brightening Night Cream",
      desc: "Infused with natural extracts for glowing, nourished, and even-toned skin overnight.",
      price: "₹1000",
      offer: "₹750"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-12.jpg",
      alt: "Rice Cream and Rose Facewash",
      title: "Rice Cream & Rose FaceWash",
      desc: "100 ML",
      price: "₹299",
      offer: "₹199"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-35.jpg",
      alt: "Ginseng Energize Facewash",
      title: "Ginseng Energize Glow FaceWash",
      desc: "100 ML",
      price: "₹299",
      offer: "₹199"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-30.jpg",
      alt: "Irish Illumination Soap",
      title: "Irish Illumination Soap",
      desc: "100 GMS",
      price: "₹199",
      offer: "₹129"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-47-56.jpg",
      alt: "Strawberry Tinted Lip Butter",
      title: "Strawberry Tinted Lip Butter",
      desc: "6 ML",
      price: "₹299",
      offer: "₹149 / Mini ₹60"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-01.jpg",
      alt: "Chocolate Tinted Lip Butter",
      title: "Chocolate Tinted Lip Butter",
      desc: "6 ML",
      price: "₹299",
      offer: "₹149 / Mini ₹60"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-07.jpg",
      alt: "Beetroot-Rose Tinted Lip Butter",
      title: "Beetroot-Rose Tinted Lip Butter",
      desc: "6 ML",
      price: "₹299",
      offer: "₹149 / Mini ₹60"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-23.jpg",
      alt: "Lumi_Glow SPF 50 Tinted Sunscreen",
      title: "Lumi_Glow SPF 50 Tinted Sunscreen",
      desc: "50 ML",
      price: "₹599",
      offer: "₹399"
    },
    {
      img: "/mnt/data/photo_2025-06-22_08-48-12.jpg",
      alt: "Hydra-Rose Mist",
      title: "Hydra-Rose Mist",
      desc: "50 ML",
      price: "₹189",
      offer: null
    }
  ];

  const filteredProducts = products.filter((product) =>
    product.title.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div className="bg-pink-50 min-h-screen">
      {/* Existing sections remain unchanged */}

      <div className="max-w-xl mx-auto px-6 pb-12">
        <h2 className="text-3xl font-bold text-rose-700 text-center mt-12 mb-6">Become a Reseller</h2>
        <form
          onSubmit={handleFormSubmit}
          className="bg-white shadow-lg rounded-xl p-6 flex flex-col gap-4 border border-rose-100"
        >
          <input
            type="text"
            name="name"
            placeholder="Your Name"
            value={formData.name}
            onChange={handleFormChange}
            required
            className="border border-gray-300 px-4 py-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-rose-300"
          />
          <input
            type="email"
            name="email"
            placeholder="Your Email"
            value={formData.email}
            onChange={handleFormChange}
            required
            className="border border-gray-300 px-4 py-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-rose-300"
          />
          <textarea
            name="message"
            placeholder="Your Message"
            value={formData.message}
            onChange={handleFormChange}
            rows="4"
            required
            className="border border-gray-300 px-4 py-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-rose-300"
          />
          <button
            type="submit"
            className="bg-rose-600 text-white py-2 rounded-lg font-medium hover:bg-rose-700"
          >
            Submit Inquiry
          </button>
        </form>
      </div>

      <footer className="bg-white border-t border-rose-100 py-6 text-center text-rose-600 text-sm">
        <div className="flex flex-col items-center gap-2">
          <p>Customer Support: <a href="tel:7972530698" className="text-rose-700 font-medium">7972530698</a></p>
          <p>Email: <a href="mailto:nooraincosmetics@gmail.com" className="text-rose-700 font-medium">nooraincosmetics@gmail.com</a></p>
          <p className="max-w-xl text-center px-4">For bulk orders or commission-based reseller inquiries, WhatsApp, DM or email us directly!</p>
          <div className="flex gap-4 justify-center mt-2">
            <a href="https://wa.me/message/FCDYEGMJYSJ6O1" target="_blank" className="hover:underline">WhatsApp</a>
            <a href="https://www.instagram.com/noorain_skincare_cosmetics?igsh=eTljMjkwd3ZwY3h3" target="_blank" className="hover:underline">Instagram</a>
            <a href="https://www.instagram.com/noorain_cosmetics?igsh=eTljMjkwd3ZwY3h3" target="_blank" className="hover:underline">Facebook</a>
          </div>
        </div>
      </footer>
    </div>
  );
}
