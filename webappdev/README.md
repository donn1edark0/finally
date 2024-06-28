# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh



- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refres


Sure, here’s a more concise version with code snippets:

### 1. UI Centering and Layout
- **Challenge**: To center the main container.
- **Used**: Flexbox.

  ```css
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  ```

### 2. Playback Controls
- **Challenge**: Designing detailed, functional controls.
- **Used**: Material-UI `IconButton`.

  ```jsx
  <Box display="flex" justifyContent="center" alignItems="center">
    <IconButton><PlayArrow /></IconButton>
    <IconButton><Pause /></IconButton>
    <IconButton><Stop /></IconButton>
  </Box>
  ```

### 3. Styling Consistency
- **Challenge**: Matching AIMP3's aesthetic.
- **Used**: Custom Material-UI theme.

  ```javascript
  const theme = createTheme({
    palette: { primary: { main: '#ff9800' }, background: { default: '#2b2b2b' } },
    typography: { fontFamily: 'Arial, sans-serif' }
  });
  ```

### 4. Volume Control Slider
- **Challenge**: Styling and functionality.
- **Used**: Material-UI `Slider`.

  ```jsx
  <Slider defaultValue={50} color="primary" onChange={(e, value) => onVolumeChange(value)} />
  ```

### 5. Fetching and Displaying Playlist
- **Challenge**: Fetching data and displaying it.
- **Used**: Axios, Material-UI `List`.

  ```jsx
  axios.get('http://localhost:5000/api/music').then(response => setSongs(response.data));
  ```

  ```jsx
  <List>
    {songs.map((song, index) => (
      <ListItem button key={index} onClick={() => onSongSelect(song)}>
        <ListItemText primary={song.title} />
      </ListItem>
    ))}
  </List>
  ```

### 6. Handling Audio Playback State
- **Challenge**: Managing play, pause, stop states.
- **Used**: React `useState`, `useRef`.

  ```jsx
  const audioRef = useRef(null);
  const [isPlaying, setIsPlaying] = useState(false);
  ```

### 7. Integrating Material-UI with Custom CSS
- **Challenge**: Overriding default styles.
- **Used**: Custom CSS with Material-UI classes.

  ```css
  .MuiIconButton-root {
    color: #ff9800;
  }
  
