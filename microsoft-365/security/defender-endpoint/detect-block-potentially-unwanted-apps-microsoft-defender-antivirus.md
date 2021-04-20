---
title: Microsoft Defender ウイルス対策を使用して望ましくない可能性のあるアプリケーションをブロックする
description: 不要と思われるアプリケーション (PUA) ウイルス対策機能を有効にして、アドウェアなどの不要なソフトウェアをブロックします。
keywords: pua, enable, unwanted software, 望ましくないアプリ, アドウェア, ブラウザー ツールバー, 検出, ブロック, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8350db473580fd4d1728c3473742da5b63196c52
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893579"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>望ましくない可能性のあるアプリケーションの検出とブロック

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

望ましくない可能性のあるアプリケーション (PUA) は、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しないソフトウェアや望ましくない可能性のある他のソフトウェアをインストールするソフトウェアのカテゴリです。 PUA はウイルス、マルウェア、その他の種類の脅威とは見なされませんが、エンドポイントのパフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。 PUA *という用語は* 、特定の種類の望ましくない動作が原因で、Microsoft Defender for Endpoint によって評価される、評判の悪いアプリケーションを参照できます。

次に例を示します。

- **広告または** プロモーションを表示する広告ソフトウェア(Web ページに広告を挿入するソフトウェアを含む)。
- **同じエンティティによって** デジタル署名されていない他のソフトウェアのインストールを提供するソフトウェアのバンドル。 また、PUA と見なす他のソフトウェアをインストールするソフトウェアも提供しています。
- **セキュリティ製品の存在** で動作が異なるソフトウェアを含む、セキュリティ製品による検出を積極的に回避しようとする Evasion ソフトウェア。

> [!TIP]
> セキュリティ機能による特別な注意のためにアプリケーションにラベルを付けするために使用する条件の詳細と条件については、「Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを識別する方法」を [参照してください](/windows/security/threat-protection/intelligence/criteria)。

望ましくない可能性のあるアプリケーションは、ネットワークが実際のマルウェアに感染するリスクを高め、マルウェア感染を特定しにくくしたり、IT リソースを無駄にしたりします。 PUA 保護は、Windows 10、Windows Server 2019、および Windows Server 2016 でサポートされています。 Windows 10 (バージョン 2004 以降) では、既定で PUA for Enterprise (E5) デバイスと見なされるアプリがブロックされます。

## <a name="microsoft-edge"></a>Microsoft Edge

クロム [ベースの新](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)しい Microsoft Edge は、望ましくない可能性のあるアプリケーションのダウンロードと関連するリソース URL をブロックします。 この機能は [、Microsoft Defender SmartScreen を介して提供されます](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)。

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>クロム ベースの Microsoft Edge で PUA 保護を有効にする

Microsoft Edge (クロム ベースのバージョン 80.0.361.50) で望ましくない可能性があるアプリケーション保護は既定で無効になっていますが、ブラウザー内から簡単にオンにできます。

1. エッジ ブラウザーで省略記号を選択し、[設定] を **選択します**。

2. [プライバシー **、検索、サービス] を選択します**。

3. [セキュリティ **] セクションで** 、[望ましくない可能性のあるアプリ **をブロックする] をオンにします**。

> [!TIP]
> Microsoft Edge (クロムベース) を実行している場合は [、Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/)デモ ページの 1 つでテストすることで、PUA 保護の URL ブロック機能を安全に確認できます。

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen を使用した URL のブロック

PUA 保護が有効になっているクロム ベースのエッジでは、Microsoft Defender SmartScreen は PUA に関連付けられた URL から保護します。

セキュリティ管理者 [は、Microsoft](/DeployEdge/configure-microsoft-edge) Edge と Microsoft Defender SmartScreen を組み合わせて PUA に関連付けられた URL からユーザーのグループを保護する方法を構成できます。 Microsoft Defender SmartScreen [には、PUA](/DeployEdge/microsoft-edge-policies#smartscreen-settings) をブロックするためのグループ ポリシー設定など、いくつかのグループ ポリシー [設定が明示的に用意されています](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。 さらに、管理者はグループ ポリシー設定を使用して [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) をオンまたはオフにし、Microsoft Defender SmartScreen 全体を構成できます。

Microsoft Defender for Endpoint には、Microsoft が管理するデータ セットに基づいて独自のブロックリストが含まれるが、独自の脅威インテリジェンスに基づいてこのリストをカスタマイズできます。 Microsoft Defender for Endpoint ポータル [で](manage-indicators.md) インジケーターを作成および管理する場合、Microsoft Defender SmartScreen は新しい設定を尊重します。

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策

Microsoft Defender Antivirus の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイントで PUA を検出およびブロックできます。

> [!NOTE]
> この機能は、Windows 10、Windows Server 2019、および Windows Server 2016 で使用できます。

Microsoft Defender Antivirus は、PUA ファイルと、PUA ファイルのダウンロード、移動、実行、またはインストールを試みる試みをブロックします。 ブロックされた PUA ファイルは検疫に移動されます。 エンドポイントで PUA ファイルが検出されると、Microsoft Defender ウイルス対策は、他の脅威検出と同じ形式で[ユーザーに通知](configure-notifications-microsoft-defender-antivirus.md)を送信します (通知が無効になっている場合を除く)。 通知は、その内容を示 `PUA:` すために前置きされます。

通知は、Windows セキュリティ アプリ内の通常 [の検疫リストに表示されます](microsoft-defender-security-center-antivirus.md)。

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策で PUA 保護を構成する

[Microsoft Intune、Microsoft Endpoint](/mem/intune/protect/device-protect)Configuration [Manager、グループ](/mem/configmgr/protect/deploy-use/endpoint-protection)ポリシー [](/azure/active-directory-domain-services/manage-group-policy)、または PowerShell コマンドレットを使用して[PUA 保護を有効にできます](/powershell/module/defender/?preserve-view=true&view=win10-ps)。

また、監査モードで PUA 保護を使用して、望ましくない可能性のあるアプリケーションをブロックせずに検出することもできます。 検出は Windows イベント ログに記録されます。

> [!TIP]
> Microsoft Defender for Endpoint のデモ web サイトを demo.wd.microsoft.com [機能が](https://demo.wd.microsoft.com/Page/UrlRep) 動作しているのを確認し、実際に動作しているのを確認してください。

監査モードでの PUA 保護は、社内のソフトウェア セキュリティ コンプライアンス チェックを実施し、誤検知を回避する場合に役立ちます。

#### <a name="use-intune-to-configure-pua-protection"></a>Intune を使用して PUA 保護を構成する

詳細 [については、「Configure device Restriction settings in Microsoft Intune」](/intune/device-restrictions-configure) および [「Microsoft Defender Antivirus device Restriction settings for Windows 10 in Intune」](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) を参照してください。

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager を使用して PUA 保護を構成する

PUA 保護は、Microsoft エンドポイント マネージャー (現在のブランチ) で既定で有効になっています。

Microsoft Endpoint Manager (Current Branch) の構成の詳細については、「マルウェア対策ポリシーを作成して展開する方法 [:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) スケジュールされたスキャン設定」を参照してください。

System Center 2012 Configuration Manager の場合は、「Configuration Manager でエンドポイント保護に望ましくない可能性のあるアプリケーション保護ポリシーを展開する方法」 [を参照してください](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。

> [!NOTE]
> Microsoft Defender ウイルス対策によってブロックされた PUA イベントは、Microsoft エンドポイント構成マネージャーではなく、Windows イベント ビューアーで報告されます。

#### <a name="use-group-policy-to-configure-pua-protection"></a>グループ ポリシーを使用して PUA 保護を構成する

1. [Windows 10 2020 年 10 月更新プログラム (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)用の管理用テンプレート (.admx) をダウンロードしてインストールする

2. グループ ポリシー管理コンピューターで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

3. 構成するグループ ポリシー オブジェクトを選択し、[編集] を **選択します**。

4. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。

5. ツリーを Windows コンポーネント Microsoft Defender ウイルス **対策**  >  **に展開します**。

6. [望ましくない **可能性があるアプリケーションの検出を構成する] をダブルクリックします**。

7. [有効 **] を** 選択して PUA 保護を有効にします。

8. [**オプション]** で、[**ブロック]** を選択して望ましくない可能性のあるアプリケーションをブロックするか、[監査モード] を選択して環境での設定の動作をテストします。 [**OK**] を選択します。

9. グループ ポリシー オブジェクトは、通常と同じ方法で展開します。

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell コマンドレットを使用して PUA 保護を構成する

##### <a name="to-enable-pua-protection"></a>PUA 保護を有効にするには

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

無効になっている場合、このコマンドレットの値 `Enabled` を設定して機能を有効にします。

##### <a name="to-set-pua-protection-to-audit-mode"></a>PUA 保護を監査モードに設定するには

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

設定は `AuditMode` 、PUA をブロックせずに検出します。

##### <a name="to-disable-pua-protection"></a>PUA 保護を無効にするには

PUA 保護を有効に保つことをお勧めします。 ただし、次のコマンドレットを使用してオフにできます。

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

このコマンドレットの値を設定して `Disabled` 、機能が有効になっている場合は無効にします。

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/index)コマンドレットを構成および実行する」を参照してください。

## <a name="view-pua-events"></a>PUA イベントの表示

PUA イベントは Windows イベント ビューアーで報告されますが、Microsoft エンドポイント マネージャーや Intune では報告されません。 コマンドレットを使用して `Get-MpThreat` 、Microsoft Defender ウイルス対策が処理した脅威を表示することもできます。 次に例を示します:

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

電子メール通知を有効にし、PUA 検出に関するメールを受信できます。

Microsoft Defender [ウイルス対策イベントの表示の詳細](troubleshoot-microsoft-defender-antivirus.md) については、「トラブルシューティング イベントの IDS」を参照してください。 PUA イベントは、イベント ID **1160 の下に記録されます**。

Microsoft Defender for Endpoint を使用している場合は、高度な検索クエリを使用して PUA イベントを表示できます。 クエリの例を次に示します。

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

## <a name="excluding-files"></a>ファイルの除外

PUA 保護によってファイルが誤ってブロックされた場合や、タスクを完了するために PUA の機能が必要な場合があります。 このような場合、ファイルを除外リストに追加できます。

詳細については、「ファイル拡張子とフォルダー [の場所に基づいて除外を構成および検証する」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。

## <a name="see-also"></a>関連項目

- [次世代の保護](microsoft-defender-antivirus-in-windows-10.md)
- [行動、ヒューリスティック、リアルタイム保護を構成する](configure-protection-features-microsoft-defender-antivirus.md)