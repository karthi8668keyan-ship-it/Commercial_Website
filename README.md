# Ex02 Commercial Website
## Date:02/11/2026

## AIM
To create a commercial website using CSS Flexbox.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for Homepage, Products / Services, About Us, Contact Details and User Account.

### STEP 5
Include social media links at the footer with copyright information.

### STEP 6
Define global styles for fonts, colors, and layout.

### STEP 7
Style the header, navigation bar, and sections.

### STEP 8
Use Flexbox for layout design.

### STEP 9
Add hover effects and transitions for interactivity.

### STEP 10
Add Images and Media.

### STEP 11
Use optimized images for a professional look.

### STEP 12
Open the HTML file in a browser to check layout and functionality.

### STEP 13
Fix styling issues and refine content placement.

### STEP 14
Deploy the website.

### STEP 15
Upload to GitHub Pages for free hosting.

## PROGRAM
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Luxe Motors</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>

    <script type="text/babel">
      const { useState } = React;

      const CheckCircle = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M20 6 9 17l-5-5" />
        </svg>
      );

      const ShieldCheck = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M12 3l7 4v5c0 5-3.5 7.5-7 9-3.5-1.5-7-4-7-9V7l7-4Z" />
          <path d="m9 12 2 2 4-4" />
        </svg>
      );

      const Banknote = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M3 7.5A2.5 2.5 0 0 1 5.5 5h13A2.5 2.5 0 0 1 21 7.5v9A2.5 2.5 0 0 1 18.5 19h-13A2.5 2.5 0 0 1 3 16.5v-9Z" />
          <path d="M3 10h18" />
          <path d="M8 14.5h8" />
          <path d="M8 10.5a2 2 0 1 1 0-4 2 2 0 0 1 0 4Z" />
        </svg>
      );

      const Truck = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M3 7h11v9H3z" />
          <path d="M14 10h3l3 3v3h-6v-6Z" />
          <circle cx="8" cy="18" r="2" />
          <circle cx="18" cy="18" r="2" />
        </svg>
      );

      const Wrench = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M14.7 6.3a3 3 0 0 1 4.2 4.2l-2.8 2.8a3 3 0 0 1-4.2-4.2l2.8-2.8Z" />
          <path d="m6 18-3 3 3-3 4.2-4.2" />
        </svg>
      );

      const ShoppingCart = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <circle cx="9" cy="19" r="1.5" />
          <circle cx="18" cy="19" r="1.5" />
          <path d="M3 4h2l2.5 10.5h10.5l2-7H6" />
        </svg>
      );

      const ChevronRight = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="m9 18 6-6-6-6" />
        </svg>
      );

      const Menu = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M3 6h18M3 12h18M3 18h18" />
        </svg>
      );

      const X = (props) => (
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" {...props}>
          <path d="M18 6 6 18M6 6l12 12" />
        </svg>
      );

      // --- DATA ---
      const CARS = [
        {
          id: 1,
          name: 'Porsche 911 Turbo S',
          type: 'Sports Coupe',
          price: 33000000,
          image: 'https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2024, engine: '3.8L Twin-Turbo Flat-6', transmission: '8-speed PDK' }
        },
        {
          id: 2,
          name: 'Audi RS7 Sportback',
          type: 'Executive Sedan',
          price: 22000000,
          image: 'https://images.unsplash.com/photo-1603584173870-7f23fdae1b7a?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2024, engine: '4.0L Twin-Turbo V8', transmission: '8-speed Tiptronic' }
        },
        {
          id: 3,
          name: 'Range Rover Autobiography',
          type: 'Luxury SUV',
          price: 30000000,
          image: 'https://images.unsplash.com/photo-1606016159991-d82e16f383e5?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2024, engine: '4.4L Twin-Turbo V8', transmission: '8-speed Automatic' }
        },
        {
          id: 4,
          name: 'BMW M8 Competition',
          type: 'Grand Tourer',
          price: 24500000,
          image: 'https://images.unsplash.com/photo-1555353540-64fd121e7d0a?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2023, engine: '4.4L Twin-Turbo V8', transmission: '8-speed M Steptronic' }
        },
        {
          id: 5,
          name: 'Aston Martin Vantage',
          type: 'Sports Coupe',
          price: 30000000,
          image: 'https://images.unsplash.com/photo-1544829099-b9a0c07fad1a?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2024, engine: '4.0L Twin-Turbo V8', transmission: '8-speed Automatic' }
        },
        {
          id: 6,
          name: 'Mercedes-AMG G 63',
          type: 'Luxury SUV',
          price: 25500000,
          image: 'https://images.unsplash.com/photo-1520031441872-265e4ff70366?auto=format&fit=crop&q=80&w=800',
          specs: { year: 2024, engine: '4.0L V8 Biturbo', transmission: '9G-TRONIC' }
        }
      ];

      const SERVICES = [
        {
          title: 'Certified Vehicles',
          description: 'Every car is rigorously inspected for quality, safety, and performance before delivery.',
          icon: ShieldCheck
        },
        {
          title: 'Easy Financing',
          description: 'Transparent payment support with flexible plans designed around your budget.',
          icon: Banknote
        },
        {
          title: 'Home Delivery',
          description: 'Fast arrangements and doorstep delivery for a hassle-free buying experience.',
          icon: Truck
        },
        {
          title: 'After-Sales Support',
          description: 'Dedicated assistance for service, maintenance, and vehicle care after purchase.',
          icon: Wrench
        }
      ];

      const formatINR = (amount) => {
        return new Intl.NumberFormat('en-IN', {
          style: 'currency',
          currency: 'INR',
          maximumFractionDigits: 0
        }).format(amount);
      };

      function App() {
        const [selectedCar, setSelectedCar] = useState(null);
        const [paymentMethod, setPaymentMethod] = useState('UPI');
        const [isModalOpen, setIsModalOpen] = useState(false);
        const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false);

        const processingFee = 25000;
        const totalAmount = selectedCar ? selectedCar.price + processingFee : 0;

        const handleAddToCart = (car) => {
          setSelectedCar(car);
          if (window.innerWidth < 1024) {
            document.getElementById('cart-panel')?.scrollIntoView({ behavior: 'smooth' });
          }
        };

        const handlePayNow = () => {
          if (!selectedCar) return;
          setIsModalOpen(true);
        };

        const handleReset = () => {
          setSelectedCar(null);
          setIsModalOpen(false);
          setPaymentMethod('UPI');
          window.scrollTo({ top: 0, behavior: 'smooth' });
        };

        return (
          <div className="min-h-screen bg-slate-950 text-slate-50 font-sans selection:bg-blue-500/30">
            <nav className="fixed w-full z-50 bg-slate-950/80 backdrop-blur-lg border-b border-white/10 transition-all">
              <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="flex justify-between items-center h-20">
                  <div className="flex items-center gap-2 cursor-pointer">
                    <div className="w-8 h-8 bg-blue-600 rounded flex items-center justify-center font-bold text-xl">L</div>
                    <span className="font-bold text-2xl tracking-wide">Luxe Motors</span>
                  </div>

                  <div className="hidden md:flex space-x-8">
                    <a href="#home" className="text-sm font-medium text-slate-300 hover:text-white transition-colors">Home</a>
                    <a href="#buy" className="text-sm font-medium text-slate-300 hover:text-white transition-colors">Buy</a>
                    <a href="#services" className="text-sm font-medium text-slate-300 hover:text-white transition-colors">Services</a>
                    <a href="#buy" className="text-sm font-medium text-slate-300 hover:text-white transition-colors">Payment</a>
                  </div>

                  <div className="md:hidden">
                    <button onClick={() => setIsMobileMenuOpen(!isMobileMenuOpen)} className="text-slate-300 hover:text-white p-2">
                      {isMobileMenuOpen ? <X size={24} /> : <Menu size={24} />}
                    </button>
                  </div>
                </div>
              </div>

              {isMobileMenuOpen && (
                <div className="md:hidden bg-slate-900 border-b border-white/10">
                  <div className="px-2 pt-2 pb-3 space-y-1 sm:px-3 flex flex-col">
                    <a href="#home" onClick={() => setIsMobileMenuOpen(false)} className="block px-3 py-2 text-base font-medium text-slate-300 hover:text-white hover:bg-slate-800 rounded-md">Home</a>
                    <a href="#buy" onClick={() => setIsMobileMenuOpen(false)} className="block px-3 py-2 text-base font-medium text-slate-300 hover:text-white hover:bg-slate-800 rounded-md">Buy</a>
                    <a href="#services" onClick={() => setIsMobileMenuOpen(false)} className="block px-3 py-2 text-base font-medium text-slate-300 hover:text-white hover:bg-slate-800 rounded-md">Services</a>
                  </div>
                </div>
              )}
            </nav>

            <section id="home" className="relative h-screen flex items-center justify-center overflow-hidden">
              <div
                className="absolute inset-0 z-0 bg-cover bg-center bg-no-repeat"
                style={{ backgroundImage: `url('https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&q=80&w=1920')` }}
              />
              <div className="absolute inset-0 z-0 bg-gradient-to-b from-slate-950/80 via-slate-950/60 to-slate-950" />

              <div className="relative z-10 text-center px-4 max-w-4xl mx-auto mt-16">
                <p className="text-blue-400 font-semibold tracking-[0.2em] uppercase text-sm mb-4">Trusted Automotive Enterprise</p>
                <h1 className="text-5xl md:text-7xl font-extrabold tracking-tight mb-6 leading-tight">
                  Drive Your Dream Car <br /> <span className="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-indigo-300">With Confidence</span>
                </h1>
                <p className="text-lg md:text-xl text-slate-300 mb-10 max-w-2xl mx-auto font-light">
                  Luxe Motors brings premium vehicles, transparent pricing, and dependable service for a smooth, trustworthy purchase experience.
                </p>
                <div className="flex flex-col sm:flex-row gap-4 justify-center">
                  <a href="#buy" className="px-8 py-4 bg-blue-600 hover:bg-blue-700 text-white rounded-full font-medium transition-all duration-300 shadow-lg shadow-blue-900/50 flex items-center justify-center gap-2">
                    Explore Cars <ChevronRight size={18} />
                  </a>
                  <a href="#services" className="px-8 py-4 bg-white/10 hover:bg-white/20 backdrop-blur-md text-white rounded-full font-medium transition-all duration-300 flex items-center justify-center">
                    Our Services
                  </a>
                </div>
              </div>
            </section>

            <section id="services" className="py-24 bg-slate-950 relative z-10">
              <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="text-center mb-16">
                  <h2 className="text-3xl md:text-4xl font-bold mb-4">Our Services</h2>
                  <p className="text-slate-400 max-w-2xl mx-auto">Everything needed to make your next vehicle purchase smooth and premium.</p>
                </div>

                <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                  {SERVICES.map((service, idx) => (
                    <div key={idx} className="bg-slate-900/50 backdrop-blur-sm border border-slate-800 p-8 rounded-3xl hover:bg-slate-800/80 transition-all duration-300 group">
                      <div className="w-12 h-12 bg-blue-900/30 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform">
                        <service.icon className="text-blue-400" size={24} />
                      </div>
                      <h3 className="text-xl font-semibold mb-3">{service.title}</h3>
                      <p className="text-slate-400 text-sm leading-relaxed">{service.description}</p>
                    </div>
                  ))}
                </div>
              </div>
            </section>

            <section id="buy" className="py-24 bg-slate-900">
              <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="text-center mb-16">
                  <h2 className="text-3xl md:text-4xl font-bold mb-4">Featured Collection</h2>
                  <p className="text-slate-400 max-w-2xl mx-auto">Luxe Motors offers premium choices with fixed prices, trusted quality, and easy purchase support.</p>
                </div>

                <div className="flex flex-col lg:flex-row gap-8 items-start">
                  <div className="flex-1 grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-6">
                    {CARS.map(car => (
                      <div key={car.id} className="bg-white rounded-3xl overflow-hidden shadow-xl hover:shadow-2xl transition-all duration-300 flex flex-col group">
                        <div className="relative h-48 overflow-hidden bg-slate-200">
                          <img src={car.image} alt={car.name} className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" />
                          <div className="absolute top-4 left-4 bg-white/90 backdrop-blur text-slate-900 text-xs font-bold px-3 py-1 rounded-full shadow">
                            {car.type}
                          </div>
                        </div>
                        <div className="p-6 flex-1 flex flex-col">
                          <h3 className="text-xl font-bold text-slate-900 mb-1">{car.name}</h3>
                          <p className="text-2xl font-extrabold text-blue-600 mb-4">{formatINR(car.price)}</p>

                          <div className="space-y-2 mb-6 text-sm text-slate-600">
                            <div className="flex justify-between border-b border-slate-100 pb-1">
                              <span>Model Year</span>
                              <span className="font-medium text-slate-900">{car.specs.year}</span>
                            </div>
                            <div className="flex justify-between border-b border-slate-100 pb-1">
                              <span>Engine</span>
                              <span className="font-medium text-slate-900">{car.specs.engine}</span>
                            </div>
                            <div className="flex justify-between pb-1">
                              <span>Transmission</span>
                              <span className="font-medium text-slate-900">{car.specs.transmission}</span>
                            </div>
                          </div>

                          <button
                            onClick={() => handleAddToCart(car)}
                            className="mt-auto w-full py-3 bg-slate-900 hover:bg-blue-600 text-white rounded-xl font-medium transition-colors flex items-center justify-center gap-2"
                          >
                            <ShoppingCart size={18} /> Select Vehicle
                          </button>
                        </div>
                      </div>
                    ))}
                  </div>

                  <div id="cart-panel" className="w-full lg:w-96 lg:sticky lg:top-28 shrink-0">
                    <div className="bg-white rounded-3xl p-6 shadow-2xl text-slate-900">
                      <h3 className="text-2xl font-bold mb-6">Cart & Payment</h3>

                      <div className="space-y-4 mb-6 text-sm">
                        <div className="flex justify-between items-center">
                          <span className="text-slate-500">Selected Vehicle</span>
                          <span className="font-semibold text-right max-w-[150px] truncate">{selectedCar ? selectedCar.name : 'None'}</span>
                        </div>
                        <div className="flex justify-between items-center">
                          <span className="text-slate-500">Car Value</span>
                          <span className="font-semibold">{selectedCar ? formatINR(selectedCar.price) : '₹0'}</span>
                        </div>
                        <div className="flex justify-between items-center">
                          <span className="text-slate-500">Processing Fee</span>
                          <span className="font-semibold">{selectedCar ? formatINR(processingFee) : '₹0'}</span>
                        </div>

                        <div className="border-t border-slate-200 my-4 pt-4 flex justify-between items-center">
                          <span className="text-base font-bold text-slate-900">Total to Pay</span>
                          <span className="text-xl font-extrabold text-blue-600">{selectedCar ? formatINR(totalAmount) : '₹0'}</span>
                        </div>
                      </div>

                      <div className="mb-6">
                        <p className="text-sm font-medium text-slate-500 mb-3">Select Payment Method</p>
                        <div className="grid grid-cols-3 gap-2">
                          {['UPI', 'Card', 'Net Banking'].map(method => (
                            <button
                              key={method}
                              disabled={!selectedCar}
                              onClick={() => setPaymentMethod(method)}
                              className={`py-2 text-xs font-semibold rounded-lg border transition-all ${
                                !selectedCar ? 'opacity-50 cursor-not-allowed bg-slate-50 border-slate-200' :
                                paymentMethod === method
                                  ? 'bg-slate-900 text-white border-slate-900'
                                  : 'bg-white text-slate-700 border-slate-200 hover:border-slate-400'
                              }`}
                            >
                              {method}
                            </button>
                          ))}
                        </div>
                      </div>

                      <button
                        onClick={handlePayNow}
                        disabled={!selectedCar}
                        className={`w-full py-4 rounded-xl font-bold text-lg transition-all shadow-lg ${
                          selectedCar
                            ? 'bg-blue-600 hover:bg-blue-700 text-white shadow-blue-600/30'
                            : 'bg-slate-100 text-slate-400 cursor-not-allowed shadow-none'
                        }`}
                      >
                        Pay Now
                      </button>

                      {!selectedCar && (
                        <p className="text-center text-xs text-slate-400 mt-4">Select a car from the collection to continue.</p>
                      )}
                    </div>
                  </div>
                </div>
              </div>
            </section>

            <footer className="bg-slate-950 py-12 border-t border-white/10">
              <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center gap-4">
                <div className="flex items-center gap-2">
                  <div className="w-6 h-6 bg-blue-600 rounded flex items-center justify-center font-bold text-sm">L</div>
                  <span className="font-bold text-lg tracking-wide">Luxe Motors</span>
                </div>
                <p className="text-slate-500 text-sm">© 2026 Luxe Motors Enterprise. All rights reserved.</p>
              </div>
            </footer>

            {isModalOpen && selectedCar && (
              <div className="fixed inset-0 z-[100] flex items-center justify-center p-4">
                <div className="absolute inset-0 bg-slate-950/80 backdrop-blur-sm" onClick={handleReset}></div>

                <div className="relative bg-white text-slate-900 w-full max-w-md rounded-3xl p-8 shadow-2xl animate-in fade-in zoom-in duration-300">
                  <div className="flex flex-col items-center text-center">
                    <div className="w-20 h-20 bg-green-100 rounded-full flex items-center justify-center mb-6">
                      <CheckCircle className="text-green-500 w-10 h-10" />
                    </div>
                    <h2 className="text-2xl font-bold mb-2">Payment Successful</h2>
                    <p className="text-slate-500 mb-8 text-sm">
                      Your vehicle booking request has been received. Our team will contact you shortly to confirm final delivery details.
                    </p>

                    <div className="w-full bg-slate-50 rounded-2xl p-5 mb-8 space-y-3 text-sm">
                      <div className="flex justify-between items-center">
                        <span className="text-slate-500">Vehicle</span>
                        <span className="font-bold text-slate-900">{selectedCar.name}</span>
                      </div>
                      <div className="flex justify-between items-center">
                        <span className="text-slate-500">Amount Paid</span>
                        <span className="font-bold text-slate-900">{formatINR(totalAmount)}</span>
                      </div>
                      <div className="flex justify-between items-center">
                        <span className="text-slate-500">Payment Method</span>
                        <span className="font-bold text-slate-900">{paymentMethod}</span>
                      </div>
                    </div>

                    <div className="flex gap-4 w-full">
                      <button
                        onClick={handleReset}
                        className="flex-1 py-3 bg-slate-900 hover:bg-slate-800 text-white rounded-xl font-semibold transition-colors"
                      >
                        Buy Another Car
                      </button>
                      <button
                        onClick={handleReset}
                        className="flex-1 py-3 bg-white hover:bg-slate-50 text-slate-900 border border-slate-200 rounded-xl font-semibold transition-colors"
                      >
                        Back Home
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            )}
          </div>
        );
      }

      const root = ReactDOM.createRoot(document.getElementById('root'));
      root.render(<App />);
    </script>
  </body>
</html>
```

## OUTPUT
<img width="1890" height="836" alt="Screenshot 2026-11-02 220042" src="https://github.com/user-attachments/assets/122b0900-806f-4387-8fec-6708ec92b9c6" />
<img width="1899" height="755" alt="Screenshot 2026-11-02 220111" src="https://github.com/user-attachments/assets/749e9971-7fcc-4aad-a80d-a365d2f6ae16" />
<img width="1885" height="760" alt="Screenshot 2026-11-02 220210" src="https://github.com/user-attachments/assets/0fa1e1cc-d8e5-46fa-8df9-03d96499bc86" />

## RESULT
The program for creating commercial website using CSS Flexbox is executed successfully.
