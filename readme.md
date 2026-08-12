# 錯誤輸入法轉換器 | Bopomofo Garbled Text Converter

一個免費、免安裝的線上工具，專門協助使用者修復因輸入法切換錯誤而產生的英數注音亂碼，例如 `su3 cl4p`。使用者可以將英數亂碼轉換成注音符號、將注音轉換成中文字，或直接一鍵將英數亂碼轉換成中文字。

A free, browser-based tool for repairing garbled text caused by an incorrect input-method mode, such as `su3 cl4p`. It can convert English-and-number input into Bopomofo symbols, convert Bopomofo into Traditional Chinese characters, or directly convert garbled input into Chinese characters in one step.

## 試玩連結 | Live Demo

**https://jenchu-begdev.github.io/input-method-garble-fixer-zh/**

## 專案特色 | Features

| 中文 | English |
|---|---|
| 將英數注音亂碼轉換成注音符號。 | Convert English-and-number Bopomofo key sequences into Bopomofo symbols. |
| 將注音符號轉換成繁體中文字。 | Convert Bopomofo symbols into Traditional Chinese characters. |
| 一鍵將英數亂碼直接轉換成中文字。 | Convert garbled English-and-number input directly into Chinese characters. |
| 支援聲調輸入，並自動選取第一個候選字。 | Supports tone input and automatically selects the first candidate character. |
| HTML 頁面內建完整注音鍵位對照表，可在介面中展開查看。 | The HTML page includes a complete Bopomofo keyboard reference table that can be expanded in the interface. |
| 可複製轉換結果，也可以清除輸入或轉換結果。 | Copy conversion results and clear input or output content. |
| 具備響應式介面，可在不同尺寸的裝置上使用。 | Provides a responsive interface for different screen sizes. |
| 提供鍵盤操作、ARIA 標籤與即時狀態提示。 | Provides keyboard operation, ARIA labels, and live status announcements. |
| 可將轉換後文字交給外部 Gemini Gem 進行錯別字校對。 | Send converted text to an external Gemini Gem for typo correction. |

## 三種轉換模式 | Conversion Modes

### 1. 亂碼 → 注音 | Garbled Text → Bopomofo

在輸入框貼上或輸入因輸入法切換錯誤而產生的英數亂碼，例如 `su3 cl4p`，按下「轉換」後，工具會將其還原成對應的注音符號。結果可以直接複製，或作為下一個轉換模式的輸入。

Paste or type garbled English-and-number input, such as `su3 cl4p`, and select “Convert”. The tool restores the corresponding Bopomofo symbols. The result can be copied or used as the input for the next conversion mode.

### 2. 注音 → 中文字 | Bopomofo → Chinese Characters

輸入注音符號與聲調，例如 `ㄋㄧˇ ㄏㄠˇ ㄇㄚ˙`，工具會根據內建的新酷音 `libchewing` 字典進行轉換，並顯示候選結果。選定或產生的中文字可以直接編輯、複製或清除。

Enter Bopomofo symbols with tones, such as `ㄋㄧˇ ㄏㄠˇ ㄇㄚ`. The tool uses the included new Chewing `libchewing` dictionary data to generate candidate characters. The selected Chinese output can be edited, copied, or cleared.

### 3. 亂碼 → 中文字 | Garbled Text → Chinese Characters

這個模式會合併前面兩個步驟，直接將英數注音亂碼轉換成中文字，適合想快速修復文字的情況。

This mode combines the previous two steps and directly converts garbled English-and-number Bopomofo input into Chinese characters for quick text repair.

## 使用方式 | How to Use

本專案是由單一 HTML 檔案組成。下載或 clone 儲存庫後，直接使用瀏覽器開啟 `index.html` 即可使用。

This project consists of a single HTML file. After downloading or cloning the repository, open `index.html` in a modern web browser.

```bash
git clone https://github.com/jenchu-begdev/input-method-garble-fixer-zh.git
```

接著在瀏覽器中開啟 `index.html`。

Then open `index.html` in your browser.

> 如果使用本機檔案開啟時，外部字型、字典資料或其他外部資源無法載入，部分功能可能會受到影響。建議使用可正常存取外部資源的瀏覽器環境，或透過靜態網站服務部署。
>
> When opening the file locally, some features may be affected if external fonts, dictionary data, or other resources cannot be loaded. A browser environment with access to external resources or deployment through a static hosting service is recommended.

## 聲調輸入 | Tone Input

注音轉換模式支援以下聲調表示方式：

The Bopomofo conversion mode supports the following tone notations:

| 中文說明 | English description |
|---|---|
| 空格可表示一聲。 | A space can represent the first tone. |
| `ˊ` 表示二聲。 | `ˊ` represents the second tone. |
| `ˇ` 表示三聲。 | `ˇ` represents the third tone. |
| `ˋ` 表示四聲。 | `ˋ` represents the fourth tone. |
| `˙` 表示輕聲。 | `˙` represents the neutral tone. |

系統會自動選取第一個候選字；由於注音可能對應多個中文字，轉換結果仍建議由使用者檢查與編輯。

The system automatically selects the first candidate character. Because one Bopomofo sequence may correspond to multiple Chinese characters, users should review and edit the result when necessary.

## AI 錯別字校對 | AI Typo Correction

當注音轉換結果出現同音錯別字或文字不自然時，介面可以將結果複製後，開啟外部的「錯別字精準校對助理」Gemini Gem。使用者需要登入 Google 帳號，進入 Gem 後將文字貼上即可進行後續校對。

When the Bopomofo conversion produces homophone errors or unnatural text, the interface can copy the result and open an external “precise typo correction assistant” Gemini Gem. A Google account sign-in is required; after opening the Gem, paste the copied text to continue the correction process.

> AI 校對功能使用外部 Google Gemini 服務，不是本 HTML 檔案內部自行執行的模型。外部服務的登入要求、可用性、隱私政策與輸出結果，均由 Google Gemini 服務本身決定。
>
> The AI correction feature uses an external Google Gemini service rather than running a model inside this HTML file. Login requirements, availability, privacy policies, and generated results are controlled by the Google Gemini service.

## 內建資料與外部資源 | Built-in Data and External Resources

本專案使用或依賴以下資料與外部資源：

This project uses or depends on the following data and external resources:

- **HTML5、CSS3 與原生 JavaScript**：建立介面、轉換流程與互動功能。
- **HTML5, CSS3, and vanilla JavaScript**: Build the interface, conversion flow, and interactions.
- **新酷音 `libchewing` 字典資料**：協助將注音轉換成中文字。
- **New Chewing `libchewing` dictionary data**: Helps convert Bopomofo into Chinese characters.
- **Google Fonts**：載入 Noto Sans TC 與 Inter 字型。
- **Google Fonts**: Loads the Noto Sans TC and Inter typefaces.
- **Google Gemini Gem**：提供外部 AI 錯別字校對引導功能。
- **Google Gemini Gem**: Provides the external AI typo-correction workflow.

如果字典資料或外部資源載入失敗，注音轉中文字與相關功能可能無法正常使用；第一個「亂碼 → 注音」功能則主要依賴頁面內的 JavaScript 邏輯。

If dictionary data or external resources fail to load, Bopomofo-to-Chinese conversion and related features may not work correctly. The first “Garbled Text → Bopomofo” mode primarily relies on JavaScript logic included in the page.

## 無障礙設計 | Accessibility

本專案包含多項無障礙設計，包括語意化 HTML、ARIA 標籤、Tab 分頁角色、鍵盤可操作控制項、可讀的焦點狀態、即時結果提示，以及輸入框與輸出區域的輔助說明。這些設計有助於使用鍵盤或螢幕閱讀器操作工具。

The project includes accessibility features such as semantic HTML, ARIA labels, tab-panel roles, keyboard-operable controls, visible focus states, live result announcements, and descriptive input and output areas. These features help users operate the tool with a keyboard or screen reader.

## 技術內容 | Technologies

| 技術 | 用途 | Technology | Purpose |
|---|---|---|---|
| HTML5 | 建立網頁結構與語意內容。 | HTML5 | Provides page structure and semantic content. |
| CSS3 | 建立深色主題、響應式版面、動畫與互動狀態。 | CSS3 | Provides the dark theme, responsive layout, animations, and interactive states. |
| 原生 JavaScript | 處理分頁、輸入、轉換、清除、複製與結果顯示。 | Vanilla JavaScript | Handles tabs, input, conversion, clearing, copying, and result rendering. |
| `libchewing` 字典資料 | 將注音符號轉換成中文字。 | `libchewing` dictionary data | Converts Bopomofo symbols into Chinese characters. |
| ARIA 與語意化標籤 | 提供鍵盤與輔助技術支援。 | ARIA and semantic markup | Supports keyboard use and assistive technologies. |

## 專案結構 | Project Structure

```text
.
├── index.html
├── README.md
└── LICENSE
```

## 瀏覽器支援 | Browser Support

建議使用支援現代 JavaScript、Clipboard API、ARIA 與響應式 CSS 的新版 Chrome、Edge、Firefox 或 Safari。實際功能可能會受到瀏覽器安全政策、外部資源連線與剪貼簿權限影響。

A recent version of Chrome, Edge, Firefox, or Safari with support for modern JavaScript, the Clipboard API, ARIA, and responsive CSS is recommended. Actual behaviour may be affected by browser security policies, external resource availability, and clipboard permissions.

## 貢獻方式 | Contributing

如果你發現轉換錯誤、字典候選字不符合預期、無障礙操作問題或介面錯誤，歡迎在 GitHub 建立 Issue 或提交 Pull Request。提交修改時，請同時測試三種轉換模式、複製功能、外部資源載入狀態，以及鍵盤與螢幕閱讀器操作。

If you find a conversion error, unexpected dictionary candidate, accessibility issue, or interface bug, feel free to open an Issue or submit a Pull Request on GitHub. When submitting changes, test all three conversion modes, the copy feature, external resource loading, and keyboard and screen-reader operation.

## 授權條款 | License

本專案採用 **MIT License**。詳細授權內容請參閱儲存庫中的 [`LICENSE`](LICENSE) 檔案。

This project is licensed under the **MIT License**. See the [`LICENSE`](LICENSE) file in the repository for the full license text.

```text
MIT License

Copyright (c) 2026 （jenchu-begdev）

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 作者 | Author

jenchu-begdev
jennychung1272@gmail.com
