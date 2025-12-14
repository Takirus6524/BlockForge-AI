# BlockForge-AI

AI-powered Minecraft project idea generator using popular cloud AI services (OpenAI, Mistral, Google Gemini). Generate creative Minecraft projects including builds, redstone contraptions, mods, plugins, datapacks, and more!

## ✨ Features

- 🤖 **Multiple AI Backends**: Choose from OpenAI ChatGPT, Mistral, or Google Gemini
- 🎮 **Minecraft-Specific Projects**: Generates builds, redstone, mods, plugins, datapacks, commands, resource packs
- 🎨 **Beautiful GUI**: Easy-to-use tkinter interface with tabs and controls
- 📜 **Project History**: Automatically saves all generated projects
- 💾 **Export Options**: Export projects as JSON, Markdown, or Text files
- ⚡ **Smart Fallback**: Auto-switches to Mistral if selected backend fails
- 🔄 **Retry Logic**: Handles rate limits and API errors gracefully

## 🎯 Minecraft Project Types

The generator can create ideas for:

- **🏗️ Build Projects**: Castles, cities, farms, landscapes, redstone-ready structures
- **⚡ Redstone Contraptions**: Auto-farms, doors, calculators, minigames, sorting systems
- **🔧 Mods**: Custom items, blocks, mobs using Fabric, Forge, or MCreator
- **🔌 Plugins**: Server plugins using Spigot/Paper API
- **📦 Datapacks**: Custom game mechanics, loot tables, crafting recipes
- **💻 Command Creations**: Command block contraptions, functions, one-command creations
- **🎨 Resource Packs**: Custom textures, models, sounds, animations

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- An API key from at least one AI service (OpenAI, Mistral, or Google Gemini)

### Installation

1. **Install Python dependencies:**
   ```bash
   pip install requests
   ```
   
   Or use the requirements file:
   ```bash
   pip install -r requirements.txt
   ```

2. **Get your API keys** (choose one or more):
   
   - **OpenAI ChatGPT**: https://platform.openai.com/account/api-keys
   - **Mistral AI**: https://console.mistral.ai/
   - **Google Gemini**: https://makersuite.google.com/app/apikey

3. **Set environment variables:**
   
   Create a `.env` file or export in your shell:
   ```bash
   export OPENAI_API_KEY="your_openai_key_here"
   export MISTRAL_API_KEY="your_mistral_key_here"
   export GEMINI_API_KEY="your_gemini_key_here"
   ```
   
   Or add to `.env` file:
   ```
   OPENAI_API_KEY=your_openai_key_here
   MISTRAL_API_KEY=your_mistral_key_here
   GEMINI_API_KEY=your_gemini_key_here
   ```

4. **Run the application:**
   ```bash
   python minecraft_generator.py
   ```

## 📖 Usage

### GUI Mode (Recommended)

1. **Launch the app**: `python minecraft_generator.py`
2. **Select AI Backend**: Choose your preferred AI service from the dropdown
3. **Set Preferences**:
   - **Minecraft Skill Level**: Beginner, Intermediate, or Advanced
   - **Interests**: e.g., "redstone, building, modding, commands"
   - **Time Available**: Weekend, 1 week, month, or open-ended
   - **Focus Area**: building/creative, redstone/technical, modding/development, etc.
4. **Generate**: Click "🤖 Generate Minecraft Project" or "🚀 Generate Now"
5. **Export**: Save your project as JSON, Markdown, or Text

### Example Output

```
🎮 AI-GENERATED MINECRAFT PROJECT IDEA
============================================================

📋 Project Name: Automatic Villager Trading Hall

📝 Description:
   Build an automated villager trading hall with redstone-powered
   villager sorting, infection/curing stations, and trading booths.

🎯 Project Type: build/redstone

🛠️  Technologies:
   • Minecraft Java Edition
   • Redstone Contraptions
   • WorldEdit (optional)

⭐ Key Features:
   • Automatic villager sorting by profession
   • Infection and curing station for discounts
   • 20+ trading booths with easy access
   • Item storage and sorting system

🏗️  Builds:
   • Trading hall structure (40x30x10 blocks)
   • Villager breeding area
   • Storage room with sorting system

⚡ Redstone:
   • Villager sorting mechanism using rails
   • Zombie-proof curing stations
   • Automatic name tag dispenser

🎯 Learning Outcomes:
   • Villager mechanics and trading optimization
   • Redstone automation techniques
   • Efficient build planning and layout

⏱️  Estimated Duration: 1-2 weeks
📊 Difficulty: intermediate
```

## 🔧 Configuration

### API Backends

The app supports three AI services. Configure at least one:

| Service | Model | Best For | Free Tier |
|---------|-------|----------|-----------|
| **OpenAI ChatGPT** | gpt-3.5-turbo | Best quality | Limited |
| **Mistral** | mistral-small-latest | Fast & reliable | Yes |
| **Google Gemini** | gemini-pro | Creative projects | Yes |

### Environment Variables

```bash
# Required: At least one API key
OPENAI_API_KEY=sk-...          # OpenAI API key
MISTRAL_API_KEY=...            # Mistral API key
GEMINI_API_KEY=...             # Google Gemini API key
```

## 📁 Project Structure

```
minecraft-project-generator/
├── minecraft_generator.py      # Main application
├── README.md                   # This file
├── requirements.txt            # Python dependencies
├── minecraft_suggestions.json  # Generated project history (auto-created)
└── .env                        # Your API keys (create this)
```

## 🐛 Troubleshooting

### "No AI backend available" Error

**Solution**: Make sure you've set at least one API key in your environment variables or `.env` file.

```bash
export MISTRAL_API_KEY="your_key_here"
```

### Rate Limit Errors (429)

**Solution**: The app automatically retries and falls back to Mistral. If all services are rate-limited:
- Wait a few minutes before generating again
- Switch to a different AI backend
- Check your API quota/billing

### "Empty response" from Google Gemini

**Solution**: 
- Retry the generation
- Switch to OpenAI or Mistral
- Simplify your preferences (fewer interests)

### API Key Not Working

**Solution**:
1. Verify your API key is correct and active
2. Check you've exported the environment variable correctly
3. Restart the application after setting environment variables
4. Check API service status on the provider's website

## 💡 Tips

- **Start Simple**: Begin with beginner projects if you're new to Minecraft
- **Mix Interests**: Combine interests like "redstone, building" for hybrid projects
- **Use History**: Review past projects in the History tab for inspiration
- **Export Everything**: Save interesting projects for later reference
- **Experiment**: Try different AI backends for varied creative ideas

## 🔐 Security

- **Never commit `.env` files** to version control
- **Keep API keys secret** - don't share them publicly
- **Use environment variables** for production deployments
- **Rotate keys** if accidentally exposed

## 📝 Requirements

```
Python >= 3.8
requests >= 2.31.0
tkinter (built-in with Python)
```

## 🎨 Customization

Want to customize the project types or add more Minecraft-specific categories? Edit the `create_project_prompt` method in `minecraft_generator.py`:

```python
def create_project_prompt(self, user_input: Dict) -> str:
    # Customize the prompt template here
    # Add your own project types, categories, or requirements
```

## 📜 License

This project is free to use and modify for personal and educational purposes.

## 🤝 Contributing

Feel free to fork and improve! Suggestions for new features:
- More Minecraft-specific project categories
- Integration with Minecraft world generation tools
- Direct export to Minecraft formats
- Datapack/mod code generation

## 🌟 Acknowledgments

- Powered by OpenAI, Mistral, and Google Gemini APIs
- Built with Python and tkinter
- Inspired by the Minecraft community's creativity

---

**Happy Building! 🎮⛏️**

Generate amazing Minecraft projects and bring your ideas to life!
