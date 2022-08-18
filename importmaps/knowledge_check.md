- Can you use import maps with npm packages?
  - use ./bin/importmap command to pin, unpin, or update npm packages in your import map which resolves the package dependencies and adds the pin to config/importmap.rb
    - ./bin/importmap is a convenience wrapper

- How do you download vendor files using import maps?
  - ./bin/importmap pin <library> --download

- How can you preload pinned modules?
  - append `preload: true` to the pin