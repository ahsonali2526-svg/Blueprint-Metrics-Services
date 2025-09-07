```jsx
import React, { useState } from "react";
import { 
  Building2, 
  Ruler, 
  FileText, 
  CheckCircle, 
  MessageCircle, 
  Mail, 
  Phone, 
  MapPin, 
  Send, 
  Download, 
  Clock, 
  Shield, 
  Star
} from "lucide-react";

const App = () => {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    phone: '',
    message: ''
  });

  const [isSubmitted, setIsSubmitted] = useState(false);

  const handleInputChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value
    });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    setIsSubmitted(true);
    // Reset form after 3 seconds
    setTimeout(() => {
      setIsSubmitted(false);
      setFormData({ name: '', email: '', phone: '', message: '' });
    }, 3000);
  };

  const projects = [
    {
      id: 1,
      title: "Luxury Condominium Complex",
      type: "Multifamily",
      description: "Complete lumber and drywall takeoff for 12-story luxury condominium with custom finishes and high-end materials.",
      image: "https://placehold.co/400x300/1e40af/ffffff?text=Blueprint+Takeoff",
      scope: "52 Units | 85,000 sq ft | 12 Weeks"
    },
    {
      id: 2,
      title: "Corporate Office Renovation",
      type: "Commercial",
      description: "Detailed drywall and framing takeoff for corporate headquarters renovation with complex ceiling systems.",
      image: "https://placehold.co/400x300/059669/ffffff?text=Office+Plans",
      scope: "3 Floors | 45,000 sq ft | 8 Weeks"
    },
    {
      id: 3,
      title: "Custom Residential Development",
      type: "Residential",
      description: "Precision material takeoffs for 24 custom single-family homes with varying architectural styles.",
      image: "https://placehold.co/400x300/374151/ffffff?text=Home+Designs",
      scope: "24 Homes | 60,000 sq ft | 16 Weeks"
    },
    {
      id: 4,
      title: "Retail Center Expansion",
      type: "Commercial",
      description: "Comprehensive lumber and drywall estimation for retail space expansion with specialty partitions.",
      image: "https://placehold.co/400x300/7c3aed/ffffff?text=Retail+Plans",
      scope: "8 Tenants | 32,000 sq ft | 6 Weeks"
    }
  ];

  const tools = [
    { name: "PlanSwift", logo: "PS", color: "bg-blue-600" },
    { name: "Bluebeam", logo: "BB", color: "bg-blue-500" },
    { name: "STACK", logo: "S", color: "bg-green-600" },
    { name: "Excel", logo: "EX", color: "bg-green-500" },
    { name: "Procore", logo: "PC", color: "bg-indigo-600" },
    { name: "PDF Architect", logo: "PA", color: "bg-red-500" }
  ];

  const services = [
    {
      title: "Lumber Takeoffs",
      description: "Precise framing material calculations with detailed cut lists and waste analysis",
      icon: <Ruler className="w-6 h-6" />
    },
    {
      title: "Drywall Estimation",
      description: "Accurate drywall, tape, mud, and accessory quantities with panel layout optimization",
      icon: <FileText className="w-6 h-6" />
    },
    {
      title: "Material Reports",
      description: "Professional takeoff reports with organized material lists and cost summaries",
      icon: <CheckCircle className="w-6 h-6" />
    },
    {
      title: "Digital Deliverables",
      description: "Editable PlanSwift files, marked PDFs, and Excel spreadsheets",
      icon: <Download className="w-6 h-6" />
    }
  ];

  const testimonials = [
    {
      name: "Michael Thompson",
      role: "Project Manager, Urban Builders",
      company: "Urban Builders Inc.",
      content: "John's takeoffs are incredibly accurate and detailed. He saved our team over 20 hours on the downtown condominium project by catching material discrepancies early. His reports are professional and easy to work with.",
      rating: 5
    },
    {
      name: "Sarah Chen",
      role: "Estimating Director",
      company: "Premier Construction Group",
      content: "We've worked with John on multiple commercial projects, and his consistency and attention to detail are unmatched. His ability to work quickly without sacrificing accuracy has made him an essential part of our estimating process.",
      rating: 5
    },
    {
      name: "David Rodriguez",
      role: "General Contractor",
      company: "Heritage Homes",
      content: "John delivers takeoffs that are not just numbers, but strategic insights. His material optimization suggestions have saved our clients thousands on lumber costs while maintaining structural integrity.",
      rating: 5
    }
  ];

  return (
    <div className="min-h-screen bg-white">
      {/* Navigation */}
      <nav className="fixed top-0 w-full bg-white/95 backdrop-blur-sm shadow-sm z-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center py-4">
            <div className="flex items-center space-x-2">
              <div className="w-10 h-10 bg-gradient-to-br from-blue-600 to-green-600 rounded-lg flex items-center justify-center">
                <Building2 className="w-6 h-6 text-white" />
              </div>
              <span className="text-xl font-bold text-gray-900">EstimatePro</span>
            </div>
            <div className="hidden md:flex space-x-8">
              <a href="#about" className="text-gray-700 hover:text-blue-600 transition-colors">About</a>
              <a href="#services" className="text-gray-700 hover:text-blue-600 transition-colors">Services</a>
              <a href="#portfolio" className="text-gray-700 hover:text-blue-600 transition-colors">Portfolio</a>
              <a href="#testimonials" className="text-gray-700 hover:text-blue-600 transition-colors">Testimonials</a>
              <a href="#contact" className="text-gray-700 hover:text-blue-600 transition-colors">Contact</a>
            </div>
            <button className="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition-colors font-medium">
              Get Quote
            </button>
          </div>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="pt-24 pb-16 bg-gradient-to-br from-blue-50 via-white to-green-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid lg:grid-cols-2 gap-12 items-center">
            <div className="space-y-8">
              <div className="space-y-4">
                <h1 className="text-4xl lg:text-6xl font-bold text-gray-900 leading-tight">
                  Accurate Material Takeoffs That Save Time & Money
                </h1>
                <p className="text-xl text-gray-600 leading-relaxed">
                  Professional lumber and drywall estimation services with precision, speed, and reliability. 
                  Trusted by contractors and builders across residential, multifamily, and commercial projects.
                </p>
              </div>
              
              <div className="flex flex-wrap gap-4">
                <button className="bg-blue-600 text-white px-8 py-4 rounded-lg hover:bg-blue-700 transition-all transform hover:scale-105 font-semibold text-lg shadow-lg">
                  Request a Sample Takeoff
                </button>
                <button className="border-2 border-gray-300 text-gray-700 px-8 py-4 rounded-lg hover:border-blue-600 hover:text-blue-600 transition-all font-semibold">
                  View Portfolio
                </button>
              </div>

              <div className="grid grid-cols-3 gap-8 pt-8">
                <div className="text-center">
                  <div className="text-3xl font-bold text-blue-600">150+</div>
                  <div className="text-gray-600">Projects Completed</div>
                </div>
                <div className="text-center">
                  <div className="text-3xl font-bold text-green-600">99.8%</div>
                  <div className="text-gray-600">Accuracy Rate</div>
                </div>
                <div className="text-center">
                  <div className="text-3xl font-bold text-indigo-600">48h</div>
                  <div className="text-gray-600">Average Turnaround</div>
                </div>
              </div>
            </div>
            
            <div className="relative">
              <div className="aspect-video bg-gradient-to-br from-blue-100 to-green-100 rounded-2xl overflow-hidden shadow-2xl">
                <img 
                  src="https://placehold.co/800x600/1e40af/ffffff?text=Construction+Estimation+Blueprints" 
                  alt="Construction blueprints and takeoff work"
                  className="w-full h-full object-cover"
                />
              </div>
              <div className="absolute -bottom-6 -right-6 bg-white p-6 rounded-xl shadow-xl border">
                <div className="flex items-center space-x-3">
                  <Shield className="w-8 h-8 text-green-600" />
                  <div>
                    <div className="font-semibold text-gray-900">100% Accuracy Guarantee</div>
                    <div className="text-sm text-gray-600">On every takeoff</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="about" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl lg:text-4xl font-bold text-gray-900 mb-4">About Me</h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              Professional construction estimator with 8+ years of experience specializing in lumber and drywall takeoffs
            </p>
          </div>

          <div className="grid lg:grid-cols-2 gap-12 items-center">
            <div className="space-y-6">
              <p className="text-lg text-gray-700 leading-relaxed">
                I'm a certified construction estimator with extensive experience in material takeoffs for residential, 
                multifamily, and commercial projects. My expertise lies in delivering precise lumber and drywall 
                estimations that help contractors and builders optimize their material purchases and reduce waste.
              </p>
              
              <p className="text-lg text-gray-700 leading-relaxed">
                Using industry-standard software like PlanSwift, Bluebeam, and STACK, I provide detailed takeoffs 
                that include material quantities, cut lists, and waste analysis. My goal is to save you time and 
                money while ensuring your projects stay on budget and on schedule.
              </p>

              <div className="grid grid-cols-2 gap-6 pt-6">
                <div className="flex items-center space-x-3">
                  <Clock className="w-5 h-5 text-blue-600" />
                  <span className="text-gray-700">48-Hour Turnaround</span>
                </div>
                <div className="flex items-center space-x-3">
                  <Shield className="w-5 h-5 text-green-600" />
                  <span className="text-gray-700">Accuracy Guaranteed</span>
                </div>
                <div className="flex items-center space-x-3">
                  <CheckCircle className="w-5 h-5 text-indigo-600" />
                  <span className="text-gray-700">Detailed Reporting</span>
                </div>
                <div className="flex items-center space-x-3">
                  <MessageCircle className="w-5 h-5 text-purple-600" />
                  <span className="text-gray-700">24/7 Communication</span>
                </div>
              </div>
            </div>

            <div className="space-y-6">
              <h3 className="text-2xl font-bold text-gray-900">Tools & Software</h3>
              <div className="grid grid-cols-2 gap-4">
                {tools.map((tool, index) => (
                  <div key={index} className="flex items-center space-x-3 p-3 bg-gray-50 rounded-lg hover:bg-gray-100 transition-colors">
                    <div className={`w-10 h-10 ${tool.color} rounded-lg flex items-center justify-center text-white font-bold text-sm`}>
                      {tool.logo}
                    </div>
                    <span className="font-medium text-gray-900">{tool.name}</span>
                  </div>
                ))}
              </div>

              <div className="bg-gradient-to-r from-blue-50 to-green-50 p-6 rounded-xl border">
                <h4 className="font-bold text-gray-900 mb-3">Project Focus Areas:</h4>
                <div className="space-y-2">
                  <div className="flex items-center space-x-2">
                    <div className="w-2 h-2 bg-blue-600 rounded-full"></div>
                    <span className="text-gray-700">Residential Construction</span>
                  </div>
                  <div className="flex items-center space-x-2">
                    <div className="w-2 h-2 bg-green-600 rounded-full"></div>
                    <span className="text-gray-700">Multifamily Developments</span>
                  </div>
                  <div className="flex items-center space-x-2">
                    <div className="w-2 h-2 bg-indigo-600 rounded-full"></div>
                    <span className="text-gray-700">Commercial Renovations</span>
                  </div>
                  <div className="flex items-center space-x-2">
                    <div className="w-2 h-2 bg-purple-600 rounded-full"></div>
                    <span className="text-gray-700">Retail & Office Spaces</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Services Section */}
      <section id="services" className="py-20 bg-gray-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl lg:text-4xl font-bold text-gray-900 mb-4">Services Offered</h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              Comprehensive material takeoff services designed to streamline your construction estimating process
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
            {services.map((service, index) => (
              <div key={index} className="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all transform hover:-translate-y-2">
                <div className="w-14 h-14 bg-gradient-to-br from-blue-600 to-green-600 rounded-lg flex items-center justify-center text-white mb-6">
                  {service.icon}
                </div>
                <h3 className="text-xl font-bold text-gray-900 mb-4">{service.title}</h3>
                <p className="text-gray-600 leading-relaxed">{service.description}</p>
              </div>
            ))}
          </div>

          <div className="mt-16 bg-white p-8 rounded-xl shadow-lg">
            <h3 className="text-2xl font-bold text-gray-900 mb-6 text-center">Deliverables You'll Receive</h3>
            <div className="grid md:grid-cols-3 gap-8">
              <div className="text-center">
                <div className="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4">
                  <FileText className="w-8 h-8 text-blue-600" />
                </div>
                <h4 className="font-bold text-gray-900 mb-2">Takeoff Reports</h4>
                <p className="text-gray-600">Professional PDF reports with organized material lists and summaries</p>
              </div>
              <div className="text-center">
                <div className="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
                  <Download className="w-8 h-8 text-green-600" />
                </div>
                <h4 className="font-bold text-gray-900 mb-2">Excel Spreadsheets</h4>
                <p className="text-gray-600">Editable Excel files with material quantities and cost calculations</p>
              </div>
              <div className="text-center">
                <div className="w-16 h-16 bg-indigo-100 rounded-full flex items-center justify-center mx-auto mb-4">
                  <CheckCircle className="w-8 h-8 text-indigo-600" />
                </div>
                <h4 className="font-bold text-gray-900 mb-2">Digital Files</h4>
                <p className="text-gray-600">PlanSwift files, marked PDFs, and source documentation</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Portfolio Section */}
      <section id="portfolio" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl lg:text-4xl font-bold text-gray-900 mb-4">Recent Projects</h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              A selection of completed takeoff projects showcasing precision and attention to detail
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-2 gap-8">
            {projects.map((project) => (
              <div key={project.id} className="bg-white rounded-xl shadow-lg overflow-hidden hover:shadow-2xl transition-all transform hover:-translate-y-2">
                <div className="relative">
                  <img 
                    src={project.image} 
                    alt={project.title}
                    className="w-full h-64 object-cover"
                  />
                  <div className={`absolute top-4 right-4 px-3 py-1 rounded-full text-sm font-semibold text-white ${project.type === 'Residential' ? 'bg-green-600' : project.type === 'Multifamily' ? 'bg-blue-600' : 'bg-indigo-600'}`}>
                    {project.type}
                  </div>
                </div>
                <div className="p-6">
                  <h3 className="text-xl font-bold text-gray-900 mb-2">{project.title}</h3>
                  <p className="text-gray-600 mb-4 leading-relaxed">{project.description}</p>
                  <div className="text-sm text-gray-500 font-medium">{project.scope}</div>
                  <div className="mt-4 flex justify-between items-center">
                    <button className="text-blue-600 hover:text-blue-800 font-medium flex items-center space-x-1">
                      <Download className="w-4 h-4" />
                      <span>View Sample</span>
                    </button>
                    <button className="text-green-600 hover:text-green-800 font-medium flex items-center space-x-1">
                      <Send className="w-4 h-4" />
                      <span>Request Quote</span>
                    </button>
                  </div>
                </div>
              </div>
            ))}
          </div>

          <div className="text-center mt-12">
            <button className="bg-gradient-to-r from-blue-600 to-green-600 text-white px-8 py-4 rounded-lg hover:from-blue-700 hover:to-green-700 transition-all transform hover:scale-105 font-semibold text-lg shadow-lg">
              View Full Portfolio
            </button>
          </div>
        </div>
      </section>

      {/* Testimonials Section */}
      <section id="testimonials" className="py-20 bg-gradient-to-br from-blue-50 to-green-50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl lg:text-4xl font-bold text-gray-900 mb-4">Client Testimonials</h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              What contractors and builders say about my takeoff services
            </p>
          </div>

          <div className="grid md:grid-cols-3 gap-8">
            {testimonials.map((testimonial, index) => (
              <div key={index} className="bg-white p-8 rounded-xl shadow-lg hover:shadow-xl transition-all">
                <div className="flex items-center mb-4">
                  {[...Array(testimonial.rating)].map((_, i) => (
                    <Star key={i} className="w-5 h-5 text-yellow-400 fill-current" />
                  ))}
                </div>
                <blockquote className="text-gray-700 leading-relaxed mb-6 italic">
                  "{testimonial.content}"
                </blockquote>
                <div className="border-t pt-4">
                  <div className="font-semibold text-gray-900">{testimonial.name}</div>
                  <div className="text-gray-600 text-sm">{testimonial.role}</div>
                  <div className="text-blue-600 text-sm font-medium">{testimonial.company}</div>
                </div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 bg-white">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="text-center mb-16">
            <h2 className="text-3xl lg:text-4xl font-bold text-gray-900 mb-4">Get in Touch</h2>
            <p className="text-xl text-gray-600 max-w-3xl mx-auto">
              Ready to streamline your material estimation process? Contact me for a free consultation and sample takeoff.
            </p>
          </div>

          <div className="grid lg:grid-cols-2 gap-12">
            <div className="space-y-8">
              <div className="bg-gradient-to-br from-blue-600 to-green-600 rounded-2xl p-8 text-white">
                <h3 className="text-2xl font-bold mb-6">Contact Information</h3>
                <div className="space-y-6">
                  <div className="flex items-center space-x-4">
                    <div className="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center">
                      <Mail className="w-6 h-6" />
                    </div>
                    <div>
                      <div className="font-semibold">Email</div>
                      <div className="text-blue-100">estimate@estimatepro.com</div>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4">
                    <div className="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center">
                      <Phone className="w-6 h-6" />
                    </div>
                    <div>
                      <div className="font-semibold">Phone</div>
                      <div className="text-blue-100">(555) 123-4567</div>
                    </div>
                  </div>
                  <div className="flex items-center space-x-4">
                    <div className="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center">
                      <MapPin className="w-6 h-6" />
                    </div>
                    <div>
                      <div className="font-semibold">Location</div>
                      <div className="text-blue-100">Denver, CO</div>
                    </div>
                  </div>
                </div>
              </div>

              <div className="flex space-x-4">
                <a href="#" className="bg-green-500 text-white px-6 py-3 rounded-lg hover:bg-green-600 transition-colors flex items-center space-x-2">
                  <svg className="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.48,2.08a1.5,1.5,0,0,0-1.77,1.07L18.24,4.6a9.57,9.57,0,0,0-1.42-1.31A1.5,1.5,0,1,0,14.7,5.43L16,6.85a13.67,13.67,0,0,1-8-8A1.5,1.5,0,1,0,5.43,1.73L6.85,3a13.7,13.7,0,0,1-2-8.14A1.5,1.5,0,0,0,2.08,0,1.52,1.52,0,0,0,2,2.78,10.81,10.81,0,0,0,8.14,10.8,1.5,1.5,0,0,0,9.86,9.86,10.81,10.81,0,0,0,10.8,8.14,1.5,1.5,0,0,0,8,6.41L6.58,5.1a13.7,13.7,0,0,1,8.14,2A1.5,1.5,0,1,0,17.25,9.86L16,8.54a9.57,9.57,0,0,0,1.31,1.42,1.5,1.5,0,0,0,2.12-2.12Z"/>
                  </svg>
                  <span>WhatsApp</span>
                </a>
                <a href="#" className="bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 transition-colors flex items-center space-x-2">
                  <svg className="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447,2.762H3.553C3.05,2.762,2.64,3.171,2.64,3.674v16.652c0,0.503,0.409,0.912,0.913,0.912h16.894 c0.503,0,0.912-0.409,0.912-0.912V3.674C21.359,3.171,20.95,2.762,20.447,2.762z M8.595,19.025H5.347V9.774h3.248V19.025z M6.971,8.571 c-1.073,0-1.944-0.874-1.944-1.947c0-1.073,0.87-1.944,1.944-1.944c1.073,0,1.947,0.871,1.947,1.944 C8.918,7.697,8.044,8.571,6.971,8.571z M19.028,19.025h-3.248v-5.132c0-1.228,0-2.807-1.704-2.807c-1.708,0-1.972,1.337-1.972,2.709v5.229 h-3.248V9.774h3.146v1.322c0.439-0.765,1.51-1.563,3.11-1.563c3.319,0,3.926,2.185,3.926,5.018V19.025z"/>
                  </svg>
                  <span>LinkedIn</span>
                </a>
              </div>
            </div>

            <div className="bg-gray-50 p-8 rounded-xl">
              {isSubmitted ? (
                <div className="text-center py-8">
                  <div className="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
                    <CheckCircle className="w-8 h-8 text-green-600" />
                  </div>
                  <h3 className="text-2xl font-bold text-gray-900 mb-2">Message Sent!</h3>
                  <p className="text-gray-600">Thank you for your inquiry. I'll get back to you within 24 hours.</p>
                </div>
              ) : (
                <form onSubmit={handleSubmit} className="space-y-6">
                  <div>
                    <label htmlFor="name" className="block text-sm font-medium text-gray-700 mb-2">Name</label>
                    <input
                      type="text"
                      id="name"
                      name="name"
                      value={formData.name}
                      onChange={handleInputChange}
                      required
                      className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                      placeholder="Your name"
                    />
                  </div>
                  <div>
                    <label htmlFor="email" className="block text-sm font-medium text-gray-700 mb-2">Email</label>
                    <input
                      type="email"
                      id="email"
                      name="email"
                      value={formData.email}
                      onChange={handleInputChange}
                      required
                      className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                      placeholder="your.email@example.com"
                    />
                  </div>
                  <div>
                    <label htmlFor="phone" className="block text-sm font-medium text-gray-700 mb-2">Phone</label>
                    <input
                      type="tel"
                      id="phone"
                      name="phone"
                      value={formData.phone}
                      onChange={handleInputChange}
                      className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                      placeholder="(555) 123-4567"
                    />
                  </div>
                  <div>
                    <label htmlFor="message" className="block text-sm font-medium text-gray-700 mb-2">Message</label>
                    <textarea
                      id="message"
                      name="message"
                      value={formData.message}
                      onChange={handleInputChange}
                      required
                      rows={5}
                      className="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                      placeholder="Tell me about your project and takeoff needs..."
                    />
                  </div>
                  <button
                    type="submit"
                    className="w-full bg-blue-600 text-white py-3 px-6 rounded-lg hover:bg-blue-700 transition-colors font-semibold text-lg"
                  >
                    Send Message
                  </button>
                </form>
              )}
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-white py-12">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="grid md:grid-cols-4 gap-8">
            <div className="md:col-span-2">
              <div className="flex items-center space-x-2 mb-4">
                <div className="w-10 h-10 bg-gradient-to-br from-blue-600 to-green-600 rounded-lg flex items-center justify-center">
                  <Building2 className="w-6 h-6 text-white" />
                </div>
                <span className="text-xl font-bold">EstimatePro</span>
              </div>
              <p className="text-gray-300 mb-4 leading-relaxed">
                Professional construction estimation services specializing in lumber and drywall takeoffs 
                for residential, multifamily, and commercial projects.
              </p>
              <div className="flex space-x-4">
                <a href="#" className="text-gray-300 hover:text-white transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.447,2.762H3.553C3.05,2.762,2.64,3.171,2.64,3.674v16.652c0,0.503,0.409,0.912,0.913,0.912h16.894 c0.503,0,0.912-0.409,0.912-0.912V3.674C21.359,3.171,20.95,2.762,20.447,2.762z M8.595,19.025H5.347V9.774h3.248V19.025z M6.971,8.571 c-1.073,0-1.944-0.874-1.944-1.947c0-1.073,0.87-1.944,1.944-1.944c1.073,0,1.947,0.871,1.947,1.944 C8.918,7.697,8.044,8.571,6.971,8.571z M19.028,19.025h-3.248v-5.132c0-1.228,0-2.807-1.704-2.807c-1.708,0-1.972,1.337-1.972,2.709v5.229 h-3.248V9.774h3.146v1.322c0.439-0.765,1.51-1.563,3.11-1.563c3.319,0,3.926,2.185,3.926,5.018V19.025z"/>
                  </svg>
                </a>
                <a href="#" className="text-gray-300 hover:text-white transition-colors">
                  <svg className="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M20.48,2.08a1.5,1.5,0,0,0-1.77,1.07L18.24,4.6a9.57,9.57,0,0,0-1.42-1.31A1.5,1.5,0,1,0,14.7,5.43L16,6.85a13.67,13.67,0,0,1-8-8A1.5,1.5,0,1,0,5.43,1.73L6.85,3a13.7,13.7,0,0,1-2-8.14A1.5,1.5,0,0,0,2.08,0,1.52,1.52,0,0,0,2,2.78,10.81,10.81,0,0,0,8.14,10.8,1.5,1.5,0,0,0,9.86,9.86,10.81,10.81,0,0,0,10.8,8.14,1.5,1.5,0,0,0,8,6.41L6.58,5.1a13.7,13.7,0,0,1,8.14,2A1.5,1.5,0,1,0,17.25,9.86L16,8.54a9.57,9.57,0,0,0,1.31,1.42,1.5,1.5,0,0,0,2.12-2.12Z"/>
                  </svg>
                </a>
              </div>
            </div>
            <div>
              <h3 className="font-semibold mb-4">Services</h3>
              <ul className="space-y-2 text-gray-300">
                <li>Lumber Takeoffs</li>
                <li>Drywall Estimation</li>
                <li>Material Reports</li>
                <li>PlanSwift Files</li>
                <li>Excel Spreadsheets</li>
              </ul>
            </div>
            <div>
              <h3 className="font-semibold mb-4">Quick Links</h3>
              <ul className="space-y-2 text-gray-300">
                <li><a href="#about" className="hover:text-white transition-colors">About</a></li>
                <li><a href="#services" className="hover:text-white transition-colors">Services</a></li>
                <li><a href="#portfolio" className="hover:text-white transition-colors">Portfolio</a></li>
                <li><a href="#testimonials" className="hover:text-white transition-colors">Testimonials</a></li>
                <li><a href="#contact" className="hover:text-white transition-colors">Contact</a></li>
              </ul>
            </div>
          </div>
          <div className="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
            <p>&copy; 2024 EstimatePro. All rights reserved.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default App;
```
