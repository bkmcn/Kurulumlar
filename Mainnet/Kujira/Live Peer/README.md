<p align="center">
  <img height="100" height="auto" src="https://raw.githubusercontent.com/Nodeist/Kurulumlar/main/logos/kujira.png">
</p>


# Kujira Live Peers
Here is a list of active peers. Add them to your `config.toml` if you have trouble finding peers.
```
e250c12df7aa910e9950e162df6b6e8ef210c8da@44.206.174.98:26656,5d0f0bc1c2d60f1d273165c5c8cefc3965c3d3c9@65.108.233.175:26656,a0927acbf1e931fc16e11e454b328c991e56d3fe@51.89.155.17:44656,0743497e30049ac8d59fee5b2ab3a49c3824b95c@198.244.200.196:26656,0179a6055fc1e36053facef08766d06186f3cd33@65.21.200.224:11856,338d79e24ce36a9580ce3e9fce8eeb84e0e6f17b@65.108.130.171:26656,2e3c72b0b6f3007a109e78864e22661dd7071c06@38.242.130.118:26656,129771a48f43b83c6144c7d282ad1da62434cc07@15.204.197.12:26656,b12591db8b67f7a78b2834b5c122299fdb6c8deb@65.108.201.154:2060,1a781f294b8c30ab0b4e54494359263e9b389ebb@141.94.219.133:11756,33029bd94bc0251ca686f4e69cf24a1c6fdcb68e@176.191.97.120:28656,e726816f42831689eab9378d5d577f1d06d25716@176.9.188.21:26656,da2673cf09dc2c124947827f4cf5e7c17114d504@142.132.202.98:26656,ecafd5cadaf3526a588550a7bc343ce2670c988d@185.16.39.231:26656,030f65339defb01b0e3ddaeaa54cbeac00dd0c74@185.182.193.89:26656,b8e8c1738a49cd6143cf83287a5087c2618ebca0@141.95.47.82:30256,26d19e5b3f3a5ebafe827dabca4ef008d9c5e6fd@168.119.15.94:26656,98a6a264d2f2f5093d317f09e71036e62aa73906@107.181.235.66:20656,d6f2eee997d108d4fde5683e31d678427376dfce@77.68.27.75:26656,ffac364ae5a9a730b49f02ba95b11878f76b7043@135.125.189.131:31095,b802fbfb83d6400639f17f2883f30a46ee6b05ad@51.210.223.185:32095,fa57c7c253be46ad9f696ee2f2c1d72cbc6a1591@146.59.52.135:31095,b209c0495852ccaa810b9ae8f65f2e404333dac1@217.174.247.59:15602,644c346a03df3dc587ae190d7d944b96a31f5eef@198.244.179.125:30329,a9a4c977ec9f4bf907ce4dc74546de166bb40497@51.81.208.63:26656,eb9742d81b436b95e324816794229a9efdaf8ea8@142.132.155.170:26656,b21f57d5054aaa4cf8e3599bbe13719a47cc02d4@141.94.193.12:14656,b1f66cdee3f626faf187f91699d82bfb9e111e42@146.59.81.18:30256,4ae125f9c9b8e2f1ac83749c2209e26056b97851@65.108.238.103:11856,15679999b404a9ee027dc9f5e795d6c4fddb6cee@51.91.152.102:20000,66c551ebcb68fe343c7e2720593dc47426813a68@93.189.30.101:26656,177872437b2a31ebb0fb740ba5bd32b0be99e280@5.79.74.229:31095,ccffabe81f2de8a81e171f93fe1209392bf9993f@65.108.234.59:26656,b80cf7882c8cab4894d41ccd4f5a00406d8b5f7d@146.59.52.48:30095,d3427d444b6909529d73025fe32a73dfea7b90d1@148.251.85.115:26656,89757803f40da51678451735445ad40d5b15e059@169.155.45.187:26656,4018be5af4189573366762fa168826b4408418db@135.125.188.17:32095,f46cdadb43b2078fba2a8b261e0109c18967fdaf@95.214.55.140:21156,c62e0701155a690616fcd3a57fa2fda444840561@65.108.76.242:32095,f6d0d3ac0c748a343368705c37cf51140a95929b@146.59.81.204:36656,471518432477e31ea348af246c0b54095d41352c@88.198.131.126:26656,3a7733d4b670a672db326bd6e5f8ae37e14a3dbd@138.201.226.227:26656,377510fb7c0ee3cacd1a46dbf13b45a4e1525fa6@141.95.124.226:32011,28c1c1a9183abf671cb0a8f6965c67428854665c@198.244.202.166:26656,3d150f6a71caca5607daff69c9049c04c37da64e@51.210.223.186:30095,d6d14f99ef25c8ffee6fa4afca40fece0c1ab9fe@107.181.229.154:20656,9dc8a19299064e8d5a414a1fc25dd0d12d9871c8@138.201.16.240:30095,380243e75be25ef7882f9f83f8215358a1622d4d@162.55.92.114:2140,82588f011491c6100d922d133f52fc23460b9231@95.217.91.238:26656,f62a0842be95a33b191879c977eed2072e37926b@57.128.20.147:30256
```

Here is a script for you to update `persistent_peers` setting with these peers in `config.toml`.

```
PEERS=e250c12df7aa910e9950e162df6b6e8ef210c8da@44.206.174.98:26656,5d0f0bc1c2d60f1d273165c5c8cefc3965c3d3c9@65.108.233.175:26656,a0927acbf1e931fc16e11e454b328c991e56d3fe@51.89.155.17:44656,0743497e30049ac8d59fee5b2ab3a49c3824b95c@198.244.200.196:26656,0179a6055fc1e36053facef08766d06186f3cd33@65.21.200.224:11856,338d79e24ce36a9580ce3e9fce8eeb84e0e6f17b@65.108.130.171:26656,2e3c72b0b6f3007a109e78864e22661dd7071c06@38.242.130.118:26656,129771a48f43b83c6144c7d282ad1da62434cc07@15.204.197.12:26656,b12591db8b67f7a78b2834b5c122299fdb6c8deb@65.108.201.154:2060,1a781f294b8c30ab0b4e54494359263e9b389ebb@141.94.219.133:11756,33029bd94bc0251ca686f4e69cf24a1c6fdcb68e@176.191.97.120:28656,e726816f42831689eab9378d5d577f1d06d25716@176.9.188.21:26656,da2673cf09dc2c124947827f4cf5e7c17114d504@142.132.202.98:26656,ecafd5cadaf3526a588550a7bc343ce2670c988d@185.16.39.231:26656,030f65339defb01b0e3ddaeaa54cbeac00dd0c74@185.182.193.89:26656,b8e8c1738a49cd6143cf83287a5087c2618ebca0@141.95.47.82:30256,26d19e5b3f3a5ebafe827dabca4ef008d9c5e6fd@168.119.15.94:26656,98a6a264d2f2f5093d317f09e71036e62aa73906@107.181.235.66:20656,d6f2eee997d108d4fde5683e31d678427376dfce@77.68.27.75:26656,ffac364ae5a9a730b49f02ba95b11878f76b7043@135.125.189.131:31095,b802fbfb83d6400639f17f2883f30a46ee6b05ad@51.210.223.185:32095,fa57c7c253be46ad9f696ee2f2c1d72cbc6a1591@146.59.52.135:31095,b209c0495852ccaa810b9ae8f65f2e404333dac1@217.174.247.59:15602,644c346a03df3dc587ae190d7d944b96a31f5eef@198.244.179.125:30329,a9a4c977ec9f4bf907ce4dc74546de166bb40497@51.81.208.63:26656,eb9742d81b436b95e324816794229a9efdaf8ea8@142.132.155.170:26656,b21f57d5054aaa4cf8e3599bbe13719a47cc02d4@141.94.193.12:14656,b1f66cdee3f626faf187f91699d82bfb9e111e42@146.59.81.18:30256,4ae125f9c9b8e2f1ac83749c2209e26056b97851@65.108.238.103:11856,15679999b404a9ee027dc9f5e795d6c4fddb6cee@51.91.152.102:20000,66c551ebcb68fe343c7e2720593dc47426813a68@93.189.30.101:26656,177872437b2a31ebb0fb740ba5bd32b0be99e280@5.79.74.229:31095,ccffabe81f2de8a81e171f93fe1209392bf9993f@65.108.234.59:26656,b80cf7882c8cab4894d41ccd4f5a00406d8b5f7d@146.59.52.48:30095,d3427d444b6909529d73025fe32a73dfea7b90d1@148.251.85.115:26656,89757803f40da51678451735445ad40d5b15e059@169.155.45.187:26656,4018be5af4189573366762fa168826b4408418db@135.125.188.17:32095,f46cdadb43b2078fba2a8b261e0109c18967fdaf@95.214.55.140:21156,c62e0701155a690616fcd3a57fa2fda444840561@65.108.76.242:32095,f6d0d3ac0c748a343368705c37cf51140a95929b@146.59.81.204:36656,471518432477e31ea348af246c0b54095d41352c@88.198.131.126:26656,3a7733d4b670a672db326bd6e5f8ae37e14a3dbd@138.201.226.227:26656,377510fb7c0ee3cacd1a46dbf13b45a4e1525fa6@141.95.124.226:32011,28c1c1a9183abf671cb0a8f6965c67428854665c@198.244.202.166:26656,3d150f6a71caca5607daff69c9049c04c37da64e@51.210.223.186:30095,d6d14f99ef25c8ffee6fa4afca40fece0c1ab9fe@107.181.229.154:20656,9dc8a19299064e8d5a414a1fc25dd0d12d9871c8@138.201.16.240:30095,380243e75be25ef7882f9f83f8215358a1622d4d@162.55.92.114:2140,82588f011491c6100d922d133f52fc23460b9231@95.217.91.238:26656,f62a0842be95a33b191879c977eed2072e37926b@57.128.20.147:30256
sed -i.bak -e "s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.kujira/config/config.toml

```