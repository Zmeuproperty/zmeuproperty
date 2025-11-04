import React from "react";
import Head from "next/head";
import { motion } from "framer-motion";
import { Button } from "@/components/ui/button";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { Mail, Phone, MapPin, CheckCircle2, Rocket, Building2, Briefcase, Wrench, Sparkles } from "lucide-react";

// Zmeu Property Inc — One-Page Website with Legal Compliance for Canada

const Section = ({ id, title, kicker, children }: { id: string; title: string; kicker?: string; children: React.ReactNode }) => (
  <section id={id} className="py-20 md:py-28">
    <div className="container mx-auto max-w-6xl px-6">
      <div className="mb-10">
        {kicker && (
          <span className="inline-flex items-center rounded-full border px-3 py-1 text-xs tracking-widest uppercase text-gray-600">{kicker}</span>
        )}
        <h2 className="mt-4 text-3xl md:text-4xl font-semibold tracking-tight">{title}</h2>
      </div>
      {children}
    </div>
  </section>
);

const Feature = ({ icon: Icon, title, desc }: { icon: any; title: string; desc: string }) => (
  <Card className="shadow-sm">
    <CardHeader className="space-y-2">
      <div className="h-10 w-10 rounded-xl bg-gray-100 flex items-center justify-center">
        <Icon className="h-5 w-5" />
      </div>
      <CardTitle className="text-xl">{title}</CardTitle>
    </CardHeader>
    <CardContent>
      <p className="text-gray-600 leading-relaxed">{desc}</p>
    </CardContent>
  </Card>
);

const Stat = ({ value, label }: { value: string; label: string }) => (
  <div className="text-center">
    <div className="text-3xl md:text-4xl font-semibold">{value}</div>
    <div className="text-gray-600 mt-1">{label}</div>
  </div>
);

const NavLink = ({ href, children }: { href: string; children: React.ReactNode }) => (
  <a href={href} className="text-sm md:text-base text-gray-700 hover:text-black transition-colors">
    {children}
  </a>
);

export default function ZmeuPropertyLanding() {
  return (
    <div className="min-h-screen w-full bg-white text-black">
      <Head>
        <title>Zmeu Property Inc | Property Management & Real Estate Investments</title>
        <meta name="description" content="Zmeu Property Inc provides property management, renovation, and investment consulting services in Winnipeg, MB. We are not a real estate brokerage or realtor." />
        <meta name="keywords" content="Winnipeg property management, real estate investment, rental management, commercial property, residential rentals, Zmeu Property, Manitoba real estate" />
        <meta name="author" content="Zmeu Property Inc" />
        <meta property="og:title" content="Zmeu Property Inc — Property Management & Investment" />
        <meta property="og:description" content="Professional property management, renovation, and investment consulting services in Manitoba." />
        <meta property="og:type" content="website" />
        <meta property="og:url" content="https://zmeuproperty.com" />
        <meta property="og:image" content="/og-image.jpg" />
        <meta name="twitter:card" content="summary_large_image" />
        <script type="application/ld+json" dangerouslySetInnerHTML={{ __html: JSON.stringify({
          "@context": "https://schema.org",
          "@type": "Organization",
          "name": "Zmeu Property Inc",
          "url": "https://zmeuproperty.com",
          "logo": "https://zmeuproperty.com/logo.png",
          "contactPoint": [{
            "@type": "ContactPoint",
            "telephone": "+1-000-000-0000",
            "contactType": "Customer Service",
            "areaServed": "CA",
            "availableLanguage": "en"
          }],
          "address": {
            "@type": "PostalAddress",
            "streetAddress": "Winnipeg, MB, Canada",
            "addressLocality": "Winnipeg",
            "addressRegion": "MB",
            "addressCountry": "CA"
          },
          "sameAs": []
        }) }} />
      </Head>

      {/* Header */}
      <header className="sticky top-0 z-50 backdrop-blur supports-[backdrop-filter]:bg-white/70 bg-white/80 border-b">
        <div className="container mx-auto max-w-6xl px-6 h-16 flex items-center justify-between">
          <a href="#hero" className="flex items-center gap-2 font-semibold">
            <span className="inline-flex h-8 w-8 items-center justify-center rounded-xl bg-black text-white">
              <Sparkles className="h-4 w-4" />
            </span>
            Zmeu Property
          </a>
          <nav className="hidden md:flex items-center gap-6">
            <NavLink href="#about">About</NavLink>
            <NavLink href="#services">Services</NavLink>
            <NavLink href="#portfolio">Portfolio</NavLink>
            <NavLink href="#results">Results</NavLink>
            <NavLink href="#testimonials">Testimonials</NavLink>
            <NavLink href="#contact">Contact</NavLink>
          </nav>
          <div className="flex items-center gap-2">
            <a href="#contact"><Button className="rounded-2xl">Contact Us</Button></a>
          </div>
        </div>
      </header>

      {/* Hero Section */}
      <section id="hero" className="relative overflow-hidden">
        <div className="container mx-auto max-w-6xl px-6 py-24 md:py-32">
          <div className="grid md:grid-cols-2 gap-10 items-center">
            <div>
              <motion.h1
                initial={{ opacity: 0, y: 20 }}
                animate={{ opacity: 1, y: 0 }}
                transition={{ duration: 0.6 }}
                className="text-4xl md:text-5xl font-semibold tracking-tight"
              >
                Property Investment & Management for Owners and Investors
              </motion.h1>
              <motion.p
                initial={{ opacity: 0, y: 20 }}
                animate={{ opacity: 1, y: 0 }}
                transition={{ duration: 0.7, delay: 0.05 }}
                className="mt-6 text-lg text-gray-700 leading-relaxed"
              >
                Zmeu Property Inc helps increase property value and profitability through professional management, renovations, and smart investment strategies. We are not a licensed real estate brokerage or realtor.
              </motion.p>
              <div className="mt-8 flex flex-col sm:flex-row gap-3">
                <a href="#portfolio"><Button size="lg" className="rounded-2xl">View Portfolio</Button></a>
                <a href="#contact"><Button size="lg" variant="outline" className="rounded-2xl">Get a Consultation</Button></a>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Footer with Legal Disclaimer */}
      <footer className="border-t bg-gray-50">
        <div className="container mx-auto max-w-6xl px-6 py-10 text-sm text-gray-600 flex flex-col md:flex-row items-center justify-between gap-3">
          <div>
            © {new Date().getFullYear()} Zmeu Property Inc — All rights reserved.
            <p className="mt-1 text-xs text-gray-500 max-w-xl">
              Zmeu Property Inc is not a licensed real estate brokerage or realtor. We provide property management, renovation, and investment consulting services only. All information is for informational purposes and not financial or legal advice.
            </p>
          </div>
          <div className="flex flex-col md:flex-row items-center gap-3 text-xs md:text-sm">
            <a className="hover:underline" href="#about">About</a>
            <span>·</span>
            <a className="hover:underline" href="#contact">Contact</a>
            <span>·</span>
            <a className="hover:underline" href="#">Privacy Policy</a>
            <span>·</span>
            <a className="hover:underline" href="#">Terms of Use</a>
          </div>
        </div>
      </footer>
    </div>
  );
}
