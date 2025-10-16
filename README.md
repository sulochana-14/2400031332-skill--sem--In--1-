import { useState } from "react";

export default function App() {
  const [item, setItem] = useState(null);
  const products = [
    { name: "Hoodie", price: "₹999", desc: "Cotton hoodie", img: "https://via.placeholder.com/200" },
    { name: "Notebook", price: "₹199", desc: "Hardcover", img: "https://via.placeholder.com/200" },
  ];

  return (
    <div>
      {products.map((p) => (
        <div key={p.name} onClick={() => setItem(p)}>
          <h3>{p.name}</h3><p>{p.price}</p>
        </div>
      ))}

      {item && (
        <div className="popup">
          <img src={item.img} alt={item.name} />
          <h2>{item.name}</h2><p>{item.desc}</p>
          <button onClick={() => setItem(null)}>Close</button>
        </div>
      )}
    </div>
  );
}
