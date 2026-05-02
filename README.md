import { motion } from 'motion/react';
import { CalendarCheck, MonitorPlay, Mic2 } from 'lucide-react';

const services = [
  {
    icon: <Mic2 className="text-[#e85d04]" size={32} />,
    title: 'Live Shows',
    description: 'High-energy live performances in solo, full band, or DJ formats. Designed for clubs, arenas, and cultural festivals.',
  },
  {
    icon: <MonitorPlay className="text-[#e85d04]" size={32} />,
    title: 'Digital Performances',
    description: 'Curated digital shows optimized for social media platforms, virtual festivals, and global streaming events.',
  },
  {
    icon: <CalendarCheck className="text-[#e85d04]" size={32} />,
    title: 'Corporate & Institutional',
    description: 'Professional appearances and performances for brand activations, cultural events, and industry showcases.',
  }
];

export function Services() {
  return (
    <section id="services" className="py-24 bg-gradient-to-b from-[#0a0a0a] to-brand-base relative">
      <div className="container mx-auto px-6 max-w-7xl">
        <div className="text-center mb-16 max-w-2xl mx-auto">
          <h2 className="text-[#e85d04] text-xs font-semibold uppercase tracking-[0.3em] mb-4">Bookings</h2>
          <h3 className="font-serif text-4xl md:text-5xl text-white mb-6">Performance Offerings</h3>
          <p className="text-gray-400 font-light">
            Bringing authentic Latin vibes to your event. Teteu connects effortlessly with audiences across generations and cultures.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
          {services.map((service, index) => (
            <motion.div
              key={index}
              initial={{ opacity: 0, y: 30 }}
              whileInView={{ opacity: 1, y: 0 }}
              viewport={{ once: true }}
              transition={{ delay: index * 0.1, duration: 0.6 }}
              className="glass-panel p-8 rounded-2xl flex flex-col items-center text-center hover:-translate-y-2 transition-transform duration-300"
            >
              <div className="mb-6 bg-[#111] w-16 h-16 rounded-full flex items-center justify-center border border-[#e85d04]/20 shadow-[0_0_15px_rgba(232,93,4,0.1)]">
                {service.icon}
              </div>
              <h4 className="text-xl font-serif text-white mb-4">{service.title}</h4>
              <p className="text-gray-400 text-sm font-light leading-relaxed">{service.description}</p>
            </motion.div>
          ))}
        </div>

        <motion.div 
          className="text-center"
          initial={{ opacity: 0 }}
          whileInView={{ opacity: 1 }}
          viewport={{ once: true }}
        >
          <a 
            href="#contact" 
            className="inline-block px-10 py-5 bg-white text-black hover:bg-[#e85d04] hover:text-white font-semibold rounded-full uppercase tracking-widest transition-colors shadow-xl"
          >
            Contact
          </a>
        </motion.div>
      </div>
    </section>
  );
}
