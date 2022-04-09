---
title: Microsoft Defender ウイルス対策が更新プログラムを受け取る方法と場所を管理する
description: Microsoft Defender ウイルス対策が保護更新プログラムを受け取る方法のフォールバック順序を管理します。
keywords: 更新プログラム, セキュリティ ベースライン, 保護, フォールバック順序, ADL, MMPC, UNC, ファイル パス, 共有, WSUS
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 04cedfa951387274261c3a7a064cf11a4b97db62
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731463"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Microsoft Defender ウイルス対策更新プログラムのソースを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

ウイルス対策の保護を最新の状態に保つことが重要です。 Microsoft Defender ウイルス対策の保護更新プログラムを管理するための次の 2 つのコンポーネントがあります。

- 更新プログラムがダウンロードされる *場所*。および
- 更新プログラムをダウンロードして適用する *タイミング*。

この記事では、更新プログラムのダウンロード元を指定する方法について説明します (これはフォールバック順序とも呼ばれます)。 更新プログラムのしくみの概要と、更新プログラムの他の側面を構成する方法 (更新のスケジュール設定など) については、「[Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策 セキュリティ インテリジェンスの更新プログラムとプラットフォーム更新プログラムは、Windows Updateを通じて配信され、2019 年 10 月 21 日 (月) 以降、すべてのセキュリティ インテリジェンス更新プログラムは SHA-2 のみ署名されます。 セキュリティ インテリジェンスを更新するには、SHA-2 をサポートするようにデバイスを更新する必要があります。 詳細については、「[Windows および WSUS の 2019 SHA-2 コード署名サポートの要件](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)」を参照してください。

<a id="fallback-order"></a>

## <a name="fallback-order"></a>フォールバック順序

通常、プライマリ ソースから更新プログラムを個別にダウンロードし、その後、ネットワーク構成に基づいて優先度の高い順に他のソースをダウンロードするようにエンドポイントを構成します。 更新プログラムは、指定した順序でソースから取得されます。 現在のソースの更新プログラムが最新でない場合は、リスト内の次のソースが直ちに使用されます。

更新プログラムが発行されると、更新プログラムのサイズを最小限に抑えるためのいくつかのロジックが適用されます。 ほとんどの場合、最新の更新プログラムと、デバイスに現在インストールされている更新プログラムの違い (デルタと呼ばれます) だけがダウンロードされて適用されます。 ただし、デルタのサイズは、次の 2 つの主な要因によって異なります。

- デバイスの最後の更新からの経過時間。および
- 更新プログラムのダウンロードと適用に使用されるソース。

エンドポイントの更新プログラムが古いほど、ダウンロードは大きくなります。 ただし、ダウンロード頻度も考慮する必要があります。 更新スケジュールの頻度が高いほど、ネットワークの使用量が増える一方で、スケジュールの頻度が低いほど、ダウンロードあたりのファイル サイズが大きくなる可能性があります。

エンドポイントが更新プログラムを取得する場所として指定できる場所は 5 つあります。

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update Service](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) <sup>[[1](#fn1)]<sup></sup>  
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [ネットワーク ファイル共有](#unc-share)
- [Microsoft Defender ウイルス対策とその他の Microsoft マルウェア対策](https://www.microsoft.com/wdsi/defenderupdates) <sup>[[2](#fn1)]<sup></sup>のセキュリティ インテリジェンス更新プログラム

(<a id="fn1">1</a>) Intune 内部定義更新サーバー - SCCM/SUP を使用して Microsoft Defender ウイルス対策 の定義更新プログラムを取得し、クライアント デバイスでブロックされている Windows Update にアクセスする必要がある場合は、共同管理に移行し、エンドポイント保護ワークロードを Intune にオフロードできます。 Intune で構成されたマルウェア対策ポリシーには、オンプレミスの WSUS を更新ソースとして使用するように構成できる "内部定義更新サーバー" のオプションがあります。 これにより、企業に対して承認される公式 WU サーバーからの更新プログラムを制御できます。また、ネットワーク トラフィックをプロキシして、公式の Windows Update ネットワークに保存するのにも役立ちます。

(<a id="fn1">2</a>) ポリシーとレジストリでは、以前の名称である Microsoft マルウェア プロテクション センター (MMPC) のセキュリティ インテリジェンスとして表示される場合があります。

Microsoft Update では、最大限の保護を確保するために、迅速なリリースが可能になります。つまり、ダウンロードの頻度が低くなります。 Windows Server Update Service、Microsoft Endpoint Configuration Manager、Microsoft セキュリティ インテリジェンスの更新プログラム、およびプラットフォーム更新プログラムのソースでは、更新の頻度が低くなります。 したがって、デルタが大きくなり、ダウンロードが大きくなる可能性があります。

> [!NOTE]
> セキュリティ インテリジェンス更新プログラムにはエンジンの更新プログラムが含まれており、月単位でリリースされます。
セキュリティ インテリジェンスの更新プログラムも 1 日に複数回配信されますが、このパッケージにはエンジンは含まれていません。


> [!IMPORTANT]
> サーバー更新サービスまたは Microsoft Update の後に [Microsoft セキュリティ インテリジェンス ページ](https://www.microsoft.com/security/portal/definitions/adl.aspx)の更新プログラム Windowsをフォールバック ソースとして設定した場合、更新プログラムは、現在の更新プログラムが最新でないと見なされた場合にのみ、セキュリティ インテリジェンス更新プログラムとプラットフォーム更新プログラムからダウンロードされます。 (既定では、Windows Server Update Service または Microsoft Update サービスから更新プログラムを適用できないのは、連続する 7 日間です)。
> ただし、[保護が最新でないとして報告されるまでの日数を設定](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)できます。<p>
> 2019 年 10 月 21 日 (月曜日) 以降、セキュリティ インテリジェンスの更新プログラムとプラットフォーム更新プログラムは SHA-2 のみ署名されます。 最新のセキュリティ インテリジェンス更新プログラムとプラットフォーム更新プログラムを取得するには、SHA-2 をサポートするようにデバイスを更新する必要があります。 詳細については、「[Windows および WSUS の 2019 SHA-2 コード署名サポートの要件](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)」を参照してください。

各ソースには、次の表に示すように、更新プログラムを発行する頻度に加えて、ネットワークの構成方法に依存する一般的なシナリオがあります。

<br/><br/>

|Location|シナリオ例|
|---|---|
|Windows Server Update Service|Windows Server Update Service を使用して、ネットワークの更新プログラムを管理しています。|
|Microsoft Update|エンドポイントを Microsoft Update に直接接続する必要があります。 これは、エンタープライズ ネットワークに不定期に接続するエンドポイントや、Windows Server Update Service を使用して更新プログラムを管理しない場合に役立ちます。|
|ファイル共有|インターネットに接続されていないデバイス (VM など) があります。 インターネットに接続された VM ホストを使用して、VM が更新プログラムを取得できるネットワーク共有に更新プログラムをダウンロードできます。 仮想デスクトップ インフラストラクチャ (VDI) 環境でファイル共有を使用する方法については、「[VDI 展開ガイド](deployment-vdi-microsoft-defender-antivirus.md)」を参照してください。|
|Microsoft エンドポイント マネージャー|Microsoft エンドポイント マネージャーを使用してエンドポイントを更新しています。|
|Microsoft Defender ウイルス対策およびその他の Microsoft マルウェア対策 (旧称 MMPC) のセキュリティ インテリジェンス更新プログラムとプラットフォーム更新プログラム|[SHA-2 をサポートするようにデバイスが更新されている必要があります](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。 Microsoft Defender ウイルス対策セキュリティ インテリジェンスとプラットフォームの更新プログラムはWindows Update経由で配信され、2019 年 10 月 21 日月曜日以降、セキュリティ インテリジェンスの更新プログラムとプラットフォーム更新プログラムは SHA-2 のみに署名されます。 <br/>最近の感染が原因で最新の保護更新プログラムをダウンロードするか、[VDI 展開](deployment-vdi-microsoft-defender-antivirus.md)の強力な基本イメージをプロビジョニングするのに役立ちます。 このオプションは通常、プライマリ ソースではなく、最終的なフォールバック ソースとしてのみ使用する必要があります。 これは、[指定された日数](/microsoft-365/security/defender-endpoint/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)の間、Windows Server Update Service または Microsoft Update から更新プログラムをダウンロードできない場合にのみ使用されます。|

更新プログラムのソースを使用する順序は、グループ ポリシー、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、WMI で管理できます。

> [!IMPORTANT]
> Windows Server Update Service をダウンロード場所として設定する場合は、場所の指定に使用する管理ツールに関係なく、更新プログラムを承認する必要があります。 Windows Server Update Service を使用して自動承認ルールを設定できます。これは、更新プログラムが少なくとも 1 日に 1 回届く場合などに役立ちます。 詳細については、「[スタンドアロンの Windows Server Update Service でエンドポイント保護更新プログラムを同期する](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)」を参照してください。

この記事の手順では、最初に順序を設定する方法と、次に **[ファイル共有]** オプションを有効にした場合の設定方法について説明します。

## <a name="use-group-policy-to-manage-the-update-location"></a>グループ ポリシーを使用して更新プログラムの場所を管理する

1. グループ ポリシーの管理マシンで、[グループ ポリシーの管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** で、**[コンピューターの構成]** に移動します。

3. **[ポリシー]** をクリックし、**[管理用テンプレート]** をクリックします。

4. **[Windows コンポーネント]** \> **[Windows Defender]** \> **[署名の更新]** の順にツリーを展開し、次の設定を構成します。

   1. **[セキュリティ インテリジェンス更新プログラムをダウンロードするためのソースの順序を定義する]** 設定をダブルクリックし、オプションを **[有効]** に設定します。

   2. 次のスクリーンショットに示すように、ソースの順序を 1 つのパイプで区切って入力します (例: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`)。

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="ソースの順序を示すグループ ポリシー設定" lightbox="../../media/wdav-order-update-sources.png":::

   3. **[OK]** をクリックします。 これにより、保護更新プログラムのソースの順序が設定されます。

   4. **[セキュリティ インテリジェンス更新プログラムをダウンロードするためのファイル共有を定義する]** 設定をダブルクリックし、オプションを **[有効]** に設定します。

   5. ファイル共有のソースを指定します。 複数のソースがある場合は、使用する順序で各ソースを 1 つのパイプで区切って入力します。 パスを示すには、[標準の UNC 表記](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc)を使用します (例: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`)。 パスを入力しない場合、VM が更新プログラムをダウンロードするときに、このソースはスキップされます。

   6. **[OK]** をクリックします。 これにより、**[... ソースの順序を定義する]** グループ ポリシー設定に、ソースが参照される場合のファイル共有の順序が設定されます。

> [!NOTE]
> Windows 10 バージョン 1703 から 1809 までの場合、ポリシー パスは **Windows コンポーネント > Microsoft Defender ウイルス対策 > 署名の更新** です。Windows 10 バージョン 1903 の場合、ポリシー パスは **Windows コンポーネント > Microsoft Defender ウイルス対策 > セキュリティ インテリジェンスの更新** です

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Configuration Manager を使用して更新プログラムの場所を管理する

Microsoft エンドポイント マネージャー (Current Branch) の構成に関する詳細については、「[Endpoint Protection のセキュリティ インテリジェンスの更新を構成する](/configmgr/protect/deploy-use/endpoint-definition-updates)」を参照してください。

## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>PowerShell コマンドレットを使用して更新プログラムの場所を管理する

更新の順序を設定するには、次の PowerShell コマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```

詳細については、次の記事を参照してください。

- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成する](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender ウイルス対策コマンドレット](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Windows Management Instrumentation (WMI) を使用して更新プログラムの場所を管理する

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

詳細については、次の記事を参照してください。

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>モバイル デバイス管理 (MDM) を使用して更新プログラムの場所を管理する

MDM の構成に関する詳細については、「[ポリシー CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) 」を参照してください。

## <a name="what-if-were-using-a-third-party-vendor"></a>サードパーティ ベンダーを使用している場合

この記事では、Microsoft Defender ウイルス対策の更新プログラムを構成および管理する方法について説明します。 ただし、サードパーティ ベンダーを使用してこれらのタスクを実行することもできます。

たとえば、Contoso が Fabrikam を採用して、Microsoft Defender ウイルス対策を含むセキュリティ ソリューションを管理したとします。 Fabrikam は通常、[Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md)、[PowerShell コマンドレット](./use-powershell-cmdlets-microsoft-defender-antivirus.md)、または [Windows コマンドライン](./command-line-arguments-microsoft-defender-antivirus.md)を使用してパッチと更新プログラムを展開します。

> [!NOTE]
> Microsoft では、Microsoft Defender ウイルス対策を管理するためのサードパーティ ソリューションをテストしません。

<a id="unc-share"></a>

## <a name="create-a-unc-share-for-security-intelligence-and-platform-updates"></a>セキュリティ インテリジェンスとプラットフォーム更新プログラム用の UNC 共有を作成する

スケジュールされたタスクを使用して MMPC サイトからセキュリティ インテリジェンスとプラットフォームの更新プログラムをダウンロードするネットワーク ファイル共有 (UNC/マップ ドライブ) を設定します。

1. 共有をプロビジョニングして更新プログラムをダウンロードするシステムで、スクリプトを保存するフォルダーを作成します。

    ```console
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. 署名の更新を保存するフォルダーを作成します。

    ```console
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. PowerShell スクリプトを [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4) からダウンロードします。

4. **[Manual Download]** をクリックします。

5. **[Download the raw nupkg file]** をクリックします。

6. ファイルを抽出します。

7. ファイル SignatureDownloadCustomTask.ps1 を、先ほど作成したフォルダー `C:\Tool\PS-Scripts\` にコピーします。

8. コマンド ラインを使用して、スケジュールされたタスクを設定します。

   > [!NOTE]
   > 更新プログラムには、完全とデルタの 2 種類があります。

   - x64 デルタの場合:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x64 完全の場合:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x86 デルタの場合:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - x86 完全の場合:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   > [!NOTE]
   > スケジュールされたタスクが作成されると、タスク スケジューラの `Microsoft\Windows\Windows Defender` で確認できます。

9. 各タスクを手動で実行し、次のフォルダーにデータ (`mpam-d.exe`、`mpam-fe.exe`、`nis_full.exe`) が含まれていることを確認します (別の場所を選択した可能性があります)。

   - `C:\Temp\TempSigs\x86`
   - `C:\Temp\TempSigs\x64`

   スケジュールされたタスクが失敗した場合は、次のコマンドを実行します。

    ```console
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```

    > [!NOTE]
    > 問題は、実行ポリシーが原因である可能性があります。

10. `C:\Temp\TempSigs` を指す共有を作成します (例: `\\server\updates`)。

    > [!NOTE]
    > 少なくとも、認証されたユーザーには "読み取り" アクセス権が必要です。 この要件は、ドメイン コンピューター、共有、NTFS (セキュリティ) にも適用されます。

11. ポリシー内の共有場所を共有に設定します。

    > [!NOTE]
    > パスに x64 (または x86) フォルダーを追加しないでください。 mpcmdrun.exe プロセスによって自動的に追加されます。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策を展開する](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理してベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
