---
title: Microsoft Defender AV 保護更新プログラムを最新のエンドポイントに適用する
description: しばらく更新されていないエンドポイントに対して更新プログラムを適用する時間と方法を定義します。
keywords: 更新プログラム、保護、古い、キャッチアップ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3f56c18b66a27adfb1384f5c3f5e6c06034247d4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691041"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>Microsoft Defender ウイルス対策の更新プログラムを管理し、最新のエンドポイントをスキャンする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus を使用すると、エンドポイントが更新を回避できる期間や、更新とスキャンが必要になる前に見逃す可能性があるスキャンの数を定義できます。 これは、デバイスが企業ネットワークや外部ネットワークに接続されがちな環境、または毎日使用されていないデバイスで特に役立ちます。

たとえば、特定の PC を使用する従業員は 3 日間休憩中で、その間は PC にログオンできません。

ユーザーが作業に戻り、PC にログオンすると、Microsoft Defender ウイルス対策は直ちに最新の保護更新プログラムを確認してダウンロードし、スキャンを実行します。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>しばらく更新していないエンドポイントのキャッチアップ保護更新プログラムを設定する

Microsoft Defender Antivirus が指定した期間保護更新プログラムをダウンロードしなかった場合は、次のログオン時に最新の更新プログラムを自動的に確認してダウンロードする設定を行います。 これは、起動時に自動更新の [ダウンロードをグローバルに無効にしている場合に便利です](manage-event-based-updates-microsoft-defender-antivirus.md)。

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>Configuration Manager を使用してキャッチアップ保護更新プログラムを構成する

1.  Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。

2.  [セキュリティ インテリジェンスの **更新プログラム] セクションに移動** し、次の設定を構成します。

    1. クライアント **コンピューターがオフラインの場合は、2** つ以上の連続したスケジュールされた更新プログラムを [はい] に設定 **します**。
    2. [If  **Configuration Manager]** をセキュリティ インテリジェンス更新プログラムのソースとして使用します。。Configuration Manager によって配信される保護更新プログラムが古いとみなされる時間を指定します。 これにより、定義されたフォールバック ソースの順序に基づいて、次の更新場所 [が使用されます](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)。

3. **[OK]** をクリックします。

4.  [更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>グループ ポリシーを使用してキャッチアップ更新機能を有効にして構成する

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

4. Microsoft Defender ウイルス対策と **署名更新プログラム> Windows コンポーネントにツリー>展開します**。

5. [キャッチアップ セキュリティ **インテリジェンスの** 更新が必要な日数を定義する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 Microsoft Defender AV で最新の保護更新プログラムを確認してダウンロードする日数を入力します。

6. **[OK]** をクリックします。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>PowerShell コマンドレットを使用してキャッチアップ保護更新プログラムを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>キャッチアップ保護更新プログラムを構成するには、Windows 管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
SignatureUpdateCatchupInterval
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>保護が古いとして報告される前の日数を設定する

また、Microsoft Defender ウイルス対策保護が古いまたは古いと見なされる日数を指定できます。 指定した日数を過ごした後、クライアントはそれ自体を古い日付として報告し、PC のユーザーにエラーを表示します。 また、WSUS または Microsoft Update を最初のソースとして設定した後でセカンダリ ソースとして MMPC を使用する場合など、Microsoft Defender Antivirus が他のソースから (定義済みのフォールバック ソースの順序に基 [づいて)](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)更新プログラムをダウンロードしようとする場合があります。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>グループ ポリシーを使用して、保護が古いと見なされる日数を指定する

1.  グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4.  [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

5.  Microsoft Defender **Antivirus >署名更新プログラム>に** ツリーを展開し、次の設定を構成します。

    1.  [スパイウェア定義 **が** 古いと見なされる日数を定義する] をダブルクリックし、オプションを [有効] に **設定します**。 Microsoft Defender AV でスパイウェア セキュリティ インテリジェンスを古い日付と見なす日数を入力します。

    2. **[OK]** をクリックします。

    3.  [ウイルス定義 **が** 古いと見なされる日数を定義する] をダブルクリックし、オプションを [有効] に **設定します**。 Microsoft Defender AV でウイルス セキュリティ インテリジェンスを古い日付と見なす日数を入力します。

    4. **[OK]** をクリックします。


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>しばらくスキャンされていないエンドポイントのキャッチアップ スキャンを設定する

Microsoft Defender ウイルス対策が強制的にスキャンを実行する前に、見逃す可能性がある連続するスケジュールされたスキャンの数を設定できます。

この機能を有効にするプロセスは次の手順で行います。

1. 少なくとも 1 つのスケジュールされたスキャンをセットアップします (「スケジュール スキャン [」を参照](scheduled-catch-up-scans-microsoft-defender-antivirus.md) )。
2. キャッチアップ スキャン機能を有効にします。
3. キャッチアップ スキャンが発生する前にスキップできるスキャンの数を定義します。

この機能は、フル スキャンとクイック スキャンの両方で有効にできます。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>グループ ポリシーを使用してキャッチアップ スキャン機能を有効にして構成する

1.  少なくとも 1 つのスケジュールされたスキャンがセットアップ済みである必要があります。

2.  グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4.  [ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。

5.  Microsoft Defender **ウイルス** 対策ソフトウェア の Windows >にツリー>展開し、次の設定を構成します。

    1.  スケジュールされたクイック スキャンを設定している場合は、[キャッチアップクイック スキャンを有効にする] 設定をダブルクリックし、オプションを [有効] に **設定します**。 
    2. スケジュールされたフル スキャンを設定している場合は、[キャッチアップフル スキャンを有効にする] 設定をダブルクリックし、オプションを [有効] に **設定します**。 **[OK]** をクリックします。
    3. [キャッチアップ **スキャンを** 強制する日数を定義する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 
    4. 次にユーザーが PC にログオンするときにスキャンが自動的に実行される前に見逃す可能性があるスキャンの数を入力します。 実行されるスキャンの種類は、[スケジュールされたスキャンに使用するスキャンの種類を指定する] **によって** 決まります (「スキャンのスケジュール」 [トピックを参照](scheduled-catch-up-scans-microsoft-defender-antivirus.md) )。 **[OK]** をクリックします。

> [!NOTE]
> グループ ポリシー設定のタイトルは、日数を参照します。 ただし、この設定は、キャッチアップ スキャンが実行される前のスキャン数 (日数ではなく) に適用されます。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>PowerShell コマンドレットを使用してキャッチアップ スキャンを構成する

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を[](/powershell/module/defender/)使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策および Defender コマンドレットを管理する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>キャッチアップ スキャンを構成するには、Windows 管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>Configuration Manager を使用してキャッチアップ スキャンを構成する

1.  Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。

2.  [スケジュールされたスキャン **] セクションに移動** し、クライアント コンピューターがオフラインの場合は、選択したスキャンの種類を強制的にスキャンします **。[** はい] **に移動します**。 

3. **[OK]** をクリックします。

4.  [更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="related-articles"></a>関連記事

- [Microsoft Defender ウイルス対策の展開](deploy-manage-report-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [イベントベースの強制的な更新の管理](manage-event-based-updates-microsoft-defender-antivirus.md)
- [モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)