# 🎮 Sephiria Set Max Player (BepInEx Plugin)

세피리아(*Sephiria*) 게임의 기본 멀티플레이 최대 인원 제한을 **17명**으로 확장해 주는 BepInEx 기반 플러그인입니다.

## 📌 기능 (Features)
- 네트워크 매니저(`NetworkManager`)의 최대 접속자 수(`maxConnections`)를 17명으로 강제 고정합니다.
- 로비 UI 및 스팀 연동 통신 객체(`FizzySteamworks`)와 연동되어 인원 제한으로 인한 튕김이나 오류를 방지합니다.

---

## 🛠️ 설치 및 적용 방법 (Installation)

1. **BepInEx 설치 (필수)**
   - [BepInEx 공식 Releases 페이지](https://github.com/bepInEx/bepInEx/releases)에서 게임 환경에 맞는 최신 버전을 다운로드하여 게임 루트 폴더(`Sephiria\`)에 압축을 풉니다.
   - 게임을 한 번 실행했다가 종료하여 `BepInEx\plugins` 폴더가 정상적으로 생성되도록 합니다.

2. **플러그인 파일 다운로드 및 배치**
   - 최신 릴리스에서 `SetMaxPlayer.dll` 파일을 다운로드합니다.
   - 게임 설치 경로 내 플러그인 폴더에 파일을 넣습니다.
     ```text
     F:\SteamLibrary\steamapps\common\Sephiria\BepInEx\plugins\SetMaxPlayer.dll
     ```

3. **의존성 라이브러리 확인**
   - 플러그인이 정상 작동하려면 Harmony 라이브러리가 필요합니다. 보통 BepInEx 기본 코어에 포함되어 있으나, 없을 경우 `0Harmony.dll`이 `BepInEx\core\` 경로에 위치해 있어야 합니다.

4. **게임 실행**
   - 게임을 실행하면 자동으로 패치가 적용되며, 멀티플레이 방을 생성할 때 17인까지 수용할 수 있게 됩니다.

---

## ⚙️ 개발 및 빌드 (Build from Source)

만약 소스 코드를 직접 수정하거나 빌드하고 싶다면, .NET Framework / C# 환경에서 아래의 레퍼런스(`reference`)를 참조하여 컴파일하세요.

```powershell
C:\Windows\Microsoft.NET\Framework\v4.0.30319\csc.exe /target:library /out:SetMaxPlayer.dll SetMaxPlayerPlugin.cs /reference:"path_to_game\Sephiria_Data\Managed\UnityEngine.CoreModule.dll" /reference:"path_to_game\BepInEx\core\0Harmony.dll" /reference:"path_to_game\BepInEx\core\BepInEx.dll" /reference:"path_to_game\Sephiria_Data\Managed\netstandard.dll" /reference:"path_to_game\Sephiria_Data\Managed\Mirror.dll"