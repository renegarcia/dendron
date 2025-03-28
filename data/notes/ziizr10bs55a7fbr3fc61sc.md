
## Add an executable to the Path

To add an executable to PowerShell's path, you'll need to update the PATH environment variable. Here are the steps:

### Method 1: Using the PATH Environment Variable (Temporary)

You can update the PATH variable for the current PowerShell session by running:

```powershell
$env:PATH += ";C:\Path\To\Executable"
```

Replace `C:\Path\To\Executable` with the actual path to the executable you want to add.

**Note:** This change is only temporary and will be lost when you close the PowerShell session.

### Method 3: Using a PowerShell Profile

You can also update the PATH variable by adding a line to your PowerShell profile. This method is useful if you want to keep your environment variables separate from your system settings.

1. Open your PowerShell profile file (usually located at `C:\Users\<YourUsername>\Documents\WindowsPowerShell\profile.ps1`).
2. Add the following line:

    ```powershell
    $env:PATH += ";C:\Path\To\Executable"
    ```

3. Save the file and restart PowerShell.

### Source

1. <https://www.blackbox.ai/share/b06ec1df-08af-4e70-bbbe-dcaecaec87f8>
