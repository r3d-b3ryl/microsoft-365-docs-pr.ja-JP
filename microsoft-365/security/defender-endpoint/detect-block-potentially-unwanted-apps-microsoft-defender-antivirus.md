---
title: Microsoft Defender ウイルス対策で望ましくない可能性のあるアプリケーションをブロックする
description: 望ましくない可能性のあるアプリケーション (PUA) のウイルス対策機能を有効にして、アドウェアなどの不要なソフトウェアをブロックします。
keywords: PUA、有効化、不要なソフトウェア、不要なアプリ、アドウェア、ブラウザー ツール バー、検出、ブロック、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d232245ffa88ab63ebe68ac104f291d006612505
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222845"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>望ましくない可能性のあるアプリケーションを検出してブロックする

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

望ましくない可能性のあるアプリケーション (PUA) は、マシンの実行速度が低下したり、予期しない広告が表示されたり、最悪の場合、予期しないまたは望ましくない可能性のある他のソフトウェアをインストールしたりする可能性のあるソフトウェアのカテゴリです。 PUA は、ウイルス、マルウェア、またはその他の種類の脅威とは見なされませんが、エンドポイントのパフォーマンスまたは使用に悪影響を与えるアクションをエンドポイントで実行する可能性があります。 *PUA* という用語は、特定の種類の望ましくない動作が原因で、Microsoft Defender for Endpoint によって評価された、評判の悪いアプリケーションを指す場合もあります。

次に、いくつかの例を示します:

- Web ページに広告を挿入するソフトウェアを含む、広告またはプロモーションを表示する **広告ソフトウェア**。
- 同じエンティティによってデジタル署名されていない他のソフトウェアのインストールを提供する **バンドル ソフトウェア**。 また、PUA として適格な他のソフトウェアのインストールを提供するソフトウェア。
- セキュリティ製品の存在下で異なる動作をするソフトウェアを含む、セキュリティ製品による検出を積極的に回避しようとする **回避ソフトウェア**。

> [!TIP]
> セキュリティ機能から特別な注意を払うアプリケーションにラベルを付けるために使用するその他の例と基準の説明については、「[Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを識別する方法](/windows/security/threat-protection/intelligence/criteria)」を参照してください。

望ましくない可能性のあるアプリケーションは、ネットワークが実際のマルウェアに感染するリスクを高めたり、マルウェア感染の特定を困難にしたり、IT リソースを浪費してそれらをクリーンアップしたりする可能性があります。 PUA 保護は、Windows 10、Windows Server 2019、および Windows Server 2016 でサポートされています。 Windows 10 (バージョン 2004 以降) では、Microsoft Defender ウイルス対策は、既定で Enterprise (E5) デバイスの PUA と見なされるアプリをブロックします。

## <a name="microsoft-edge"></a>Microsoft Edge

Chromium ベースの[新しい Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea) は、望ましくない可能性のあるアプリケーションのダウンロードと関連するリソース URL をブロックします。 この機能は、[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) を介して提供されます。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Chromium ベースの Microsoft Edge で PUA 保護を有効にする

Microsoft Edge (Chromium ベース、バージョン 80.0.361.50) の望ましくない可能性のあるアプリケーション保護は既定でオフになっていますが、ブラウザー内から簡単にオンにすることができます。

1. Edge ブラウザーで、楕円を選択し、**[設定]** を選択します。

2. **[プライバシー、検索、およびサービス]** を選択します。

3. **[セキュリティ]** セクションで、**[望ましくない可能性のあるアプリをブロックする]** をオンにします。

> [!TIP]
> Microsoft Edge (Chromium ベース) を実行している場合は、[Microsoft Defender SmartScreen デモ ページ](https://demo.smartscreen.msft.net/)の 1 つでテストすることにより、PUA 保護の URL ブロック機能を安全に調べることができます。

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen で URL をブロックする

PUA 保護がオンになっている Chromium ベースの Edge では、Microsoft Defender SmartScreen が PUA に関連付けられた URL からユーザーを保護します。

セキュリティ管理者は、Microsoft Edge と Microsoft Defender SmartScreen が連携して PUA に関連付けられた URL からユーザーのグループを保護する方法を[構成](/DeployEdge/configure-microsoft-edge)できます。 [PUA をブロックするためのもの](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)を含め、Microsoft Defender SmartScreen に対して明示的に使用可能ないくつかの[グループ ポリシー設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings)があります。 さらに、管理者は、グループ ポリシー設定を使用して Microsoft Defender SmartScreen をオンまたはオフにして、[Microsoft Defender SmartScreen 全体を構成](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)できます。

Microsoft Defender for Endpoint には、Microsoft が管理するデータ セットに基づく独自のブロックリストがありますが、独自の脅威インテリジェンスに基づいてこのリストをカスタマイズできます。 Microsoft Defender for Endpoint ポータルで[インジケーターを作成および管理](manage-indicators.md)する場合、Microsoft Defender SmartScreen は新しい設定を尊重します。

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender ウイルス対策および PUA 保護

Microsoft Defender ウイルス対策の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイント上の PUA を検出してブロックできます。

> [!NOTE]
> この機能は、Windows 10、Windows Server 2019、および Windows Server 2016 で使用できます。

Windows Defender ウイルス対策は、検出された PUA ファイルと、それらのダウンロード、移動、実行、またはインストールの試行をブロックします。 ブロックされた PUA ファイルは、検疫に移動されます。 エンドポイントで PUA ファイルが検出されると、Microsoft Defender ウイルス対策は、他の脅威の検出と同じ形式でユーザーに通知を送信します ([通知が無効になっていない場合](configure-notifications-microsoft-defender-antivirus.md))。 通知の前には、その内容を示す `PUA:` が付いています。

通知は、[Windows セキュリティ アプリ内の通常の検疫リスト](microsoft-defender-security-center-antivirus.md)に表示されます。

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Windows Defender ウイルス対策で PUA 保護を構成する

PUA 保護は、[Microsoft Intune](/mem/intune/protect/device-protect)、[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection)、[グループ ポリシー](/azure/active-directory-domain-services/manage-group-policy)、または [PowerShell コマンドレット](/powershell/module/defender/?preserve-view=true&view=win10-ps)を使用して有効にできます。

監査モードで PUA 保護を使用して、望ましくない可能性のあるアプリケーションをブロックせずに検出することもできます。 検出は、Windows イベント ログに記録されます。

> [!TIP]
> Microsoft Defender for Endpoint のデモ Web サイト [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) にアクセスすることで、この機能が動作していることを確認し、実際の操作を見ることができます。

監査モードの PUA 保護は、会社が内部ソフトウェア セキュリティ コンプライアンス チェックを実施していて、誤検知を回避したい場合に役立ちます。

### <a name="use-intune-to-configure-pua-protection"></a>Intune を使用して PUA 保護を構成する

詳細については、「[Microsoft Intune でデバイスの制限設定を構成する](/intune/device-restrictions-configure)」および「[Intune での Windows 10 の Microsoft Defender ウイルス対策デバイス制限設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)」を参照してください。

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager を使用して PUA 保護を構成する

PUA 保護は、Microsoft Endpoint Manager (Current Branch) で既定で有効になっています。

Microsoft Endpoint Manager (Current Branch) の構成の詳細については、「[マルウェア対策ポリシーを作成および展開する方法: スケジュールされたスキャンの設定](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)」を参照してください。

System Center 2012 Configuration Manager については、「[Configuration Manager でエンドポイント保護のために望ましくない可能性のあるアプリケーション保護ポリシーを展開する方法](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)」を参照してください。

> [!NOTE]
> Windows Defender ウイルス対策によってブロックされた PUA イベントは、Microsoft Endpoint Configuration Manager ではなく Windows イベント ビューアーで報告されます。

### <a name="use-group-policy-to-configure-pua-protection"></a>グループ ポリシーを使用して PUA 保護を構成する

1. [2020 年 10 月更新 (20H2) Windows 10 用の管理用テンプレート (.admx)](https://www.microsoft.com/download/details.aspx?id=102157) をダウンロードしてインストールする

2. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。

3. 構成するグループ ポリシー オブジェクトを選択し、**[編集]** を選択します。

4. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

5. **[Windows コンポーネント]** \> **[Microsoft Defender ウイルス対策]** の順にツリーを展開します。

6. **[望ましくない可能性のあるアプリケーションの検出を構成する]** をダブルクリックします。

7. PUA 保護を有効にするには、**[有効]** を選択します。

8. **[オプション]** で、**[ブロック]** を選択して望ましくない可能性のあるアプリケーションをブロックするか、**[監査モード]** を選択して環境で設定がどのように機能するかをテストします。 **[OK]** を選択します。

9. 通常どおりにグループ ポリシー オブジェクトを展開します。

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell コマンドレットを使用して PUA 保護を構成する

#### <a name="to-enable-pua-protection"></a>PUA 保護を有効にするには

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

このコマンドレットの値を `Enabled` に設定すると、機能が無効になっている場合にオンになります。

#### <a name="to-set-pua-protection-to-audit-mode"></a>PUA 保護を監査モードに設定するには

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

`AuditMode` の設定により、PUA をブロックせずに検出します。

#### <a name="to-disable-pua-protection"></a>PUA 保護を無効にするには

PUA 保護をオンにしておくことをお勧めします。 ただし、次のコマンドレットを使用してオフにすることができます。

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

このコマンドレットの値を `Disabled` に設定すると、機能が有効になっている場合にオフになります。

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/index)」を参照してください。

## <a name="view-pua-events-using-powershell"></a>PowerShell を使用して PUA イベントを表示する

PUA イベントは Windows イベント ビューアーで報告されますが、Microsoft Endpoint Manager や Intune では報告されません。 `Get-MpThreat` コマンドレットを使用して、Microsoft Defender ウイルス対策が処理した脅威を表示することもできます。 次に例を示します:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>PUA 検出に関するメール通知を取得する

メール通知をオンにして、PUA 検出に関するメールを受信できます。

Microsoft Defender ウイルス対策イベントの表示の詳細については、「[イベント ID のトラブルシューティング](troubleshoot-microsoft-defender-antivirus.md)」を参照してください。 PUA イベントは、イベント ID **1160** で記録されます。

## <a name="view-pua-events-using-advanced-hunting"></a>高度な追求を使用して PUA イベントを表示する

[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を使用している場合は、高度な追求クエリを使用して PUA イベントを表示できます。 クエリの例を次に示します:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

高度な追求の詳細については、「[高度な追求を使用して脅威をプロアクティブにハントする](advanced-hunting-overview.md)」を参照してください。

## <a name="exclude-files-from-pua-protection"></a>PUA 保護からファイルを除外する

ファイルが PUA 保護によって誤ってブロックされたり、タスクを完了するために PUA の機能が必要になったりすることがあります。 このような場合、ファイルを除外リストに追加できます。

詳細については、「[ファイル拡張子とフォルダーの場所に基づく除外の構成と検証](configure-extension-file-exclusions-microsoft-defender-antivirus.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [次世代の保護](microsoft-defender-antivirus-in-windows-10.md)
- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)