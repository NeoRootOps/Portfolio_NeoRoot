<Div align="center">
  
# 📦 FICHE DE DIAGNOSTIC RÉSEAU – MODÈLE OSI

</Div>

</br>

| Couche         | Vérifications essentielles                                                                  | Commandes / Outils                                    |
|----------------|---------------------------------------------------------------------------------------------|-------------------------------------------------------|
| **P**hysique   | Câble branché, Wi-Fi actif, LED allumées, carte réseau OK                                   | Vérification visuelle / Gestionnaire de périphériques |
| **L**iaison    | MAC présente, carte reconnue, table ARP cohérente                                           | `arp -a`                                              |
| **R**éseau     | IP valide, ping local, ping passerelle, ping Internet, routes OK                            | `ipconfig` / `ip a` / `ping` / `tracert` / `route`    |
| **T**ransport  | Ports TCP/UDP ouverts, test de port                                                         | `Test-NetConnection` / `nc -zv`                       |
| **S**ession    | Session VPN/SSH active, pas de timeout                                                      | `openvpn` / `ssh`                                     |
| **P**résentation  | Certificat SSL/TLS valide, encodage correct (UTF‑8, JSON, HTML)                          | Navigateur / `openssl`                                |
| **A**pplication   | DNS OK, service web/app fonctionnel, pas de proxy incorrect                              | `nslookup` / `dig` / `curl` / navigateur              |

 - **P**our **L**a **R**oute **T**u **S**uis **P**ierre **A**ntoine - **(PLRTSPA)**

---

</br>
</br>

## 1. Physique (P)
- Vérifier câble Ethernet, LED vert/orange, ports actifs.
- Vérifier Wi-Fi : SSiD correct, signal suffisant.
- Vérifier carte réseau : activée, sans erreur.

## 2. Liaison (L)
- Vérifier présence d’une adresse MAC.
- Vérifier lien L2 (switch/box).
- Vérifier table ARP : `arp -a` → MAC de la passerelle visible.

## 3. Réseau (R)
- Vérifier IP valide (pas de 169.254.x.x).
- Ping pile locale : `ping 127.0.0.1`
- Ping passerelle : `ping 192.168.1.1`
- Ping Internet : `ping 8.8.8.8`
- Route : `tracert 8.8.8.8` ou `traceroute 8.8.8.8`

## 4. Transport (T)
- Vérifier filtrage TCP/UDP (pare-feu local / routeur).
- Test port TCP :
  - Windows : `Test-NetConnection google.com -Port 443`
  - Linux/Mac : `nc -zv google.com 443`

## 5. Session (S)
- Vérifier session VPN/SSH : connexion stable.
- Vérifier absence de timeout ou déconnexion.

## 6. Présentation (P)
- Vérifier certificat SSL/TLS (pas d’erreur navigateur).
- Vérifier encodage (UTF‑8, JSON, HTML lisible).

## 7. Application (A)
- Vérifier DNS : `nslookup google.com` / `dig google.com`
- Vérifier absence de proxy mal configuré.
- Vérifier statut du service (HTTP 200 attendu).

---

## Interprétation rapide
- **Physique** → câble / Wi-Fi / carte réseau  
- **Liaison** → switch / ARP / MAC  
- **Réseau** → IP / passerelle / DHCP  
- **Transport** → ports / pare-feu / NAT  
- **Session** → VPN / SSH / timeout  
- **Présentation** → certificat / encodage  
- **Application** → DNS / proxy / serveur distant
