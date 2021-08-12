---
title: Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御
description: Microsoft Defender for Endpoint の概要
keywords: リムーバブル 記憶域メディア
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4765477c4faf583fd9906aaa700aafc3fb26a992172f81eb4d3f6978724724be
ms.sourcegitcommit: 4f074a8598a430344a2361728a64b8b8c0e1d215
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54520698"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender for Endpoint Device Control リムーバブル Storageアクセス制御を使用すると、次のタスクを実行できます。

- 除外の付いたリムーバブル 記憶域への読み取り、書き込み、または実行アクセスの監査、許可、または防止

<br>

****

|特権|アクセス許可|
|---|---|
|Access|読み取り、書き込み、実行|
|アクション モード|監査、許可、防止|
|CSP サポート|はい|
|GPO サポート|はい|
|ユーザー ベースのサポート|はい|
|コンピューター ベースのサポート|はい|
|||

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

マルウェア対策クライアント Storage **4.18.2103.3** 以降の Windows 10 デバイスにリムーバブル アクセス制御を展開します。

- **4.18.2104** 以降: SerialNumberId の追加、VID_PID、ファイルパス ベースの GPO のサポート、ComputerSid
- **4.18.2105** 以降 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートの追加、特定のコンピューター上の特定のユーザーの組み合わせ、削除可能な SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート
- **4.18.2107** 以降 : ポータブル Windows (WPD) のサポートを追加する (タブレットなどのモバイル デバイスの場合)

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス":::

> [!NOTE]
> リムーバブル アクセスWindows セキュリティ状態とは別にリムーバブル アクセス制御を実行Storage、すべてのコンポーネントをアクティブWindows セキュリティ必要があります。

## <a name="policy-properties"></a>ポリシーのプロパティ

次のプロパティを使用して、リムーバブル 記憶域グループを作成できます。

### <a name="property-name-group-id"></a>プロパティ名: グループ ID

**説明**: 一意の ID である GUID は、グループを表し、ポリシーで使用されます。

### <a name="property-name-descriptoridlist"></a>プロパティ名: DescriptorIdList

**説明**: グループ内で使用するデバイス プロパティを一覧表示します。

各デバイス プロパティの詳細については、上記 **の「デバイスのプロパティ** 」セクションを参照してください。

**オプション**:

- プライマリ ID
  - RemovableMediaDevices
  - CdRomDevices
- DeviceId
- HardwareId
- InstancePathId: InstancePathId は、システム内のデバイスを一意に識別する文字列です (たとえば、USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0)。

末尾の番号 (たとえば、&**0)** は使用可能なスロットを表し、デバイス間で変更される場合があります。 最適な結果を得る場合は、末尾にワイルドカードを使用します。 たとえば、`USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*` などです。

- FriendlyNameId
- SerialNumberId
- VID
- PID
- VID_PID
  - 0751_55E0: この完全な VID/PID ペアと一致する
  - _55E0: PID=55E0 で任意のメディアを一致する
  - 0751_: 任意のメディアを VID=0751 と一致する

### <a name="property-name-matchtype"></a>プロパティ名: MatchType

**説明**: DescriptorIDList で複数のデバイス プロパティが使用されている場合、MatchType はリレーションシップを定義します。

**オプション**:

- MatchAll: DescriptorIdList の下の属性は **And** リレーションシップです。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、システムは USB が両方の値を満たするかどうかを確認します。
- MatchAny: DescriptorIdList の下の属性は **Or リレーションシップ** です。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは強制を実行します。

アクセス制御ポリシーのプロパティは次のとおりです。

### <a name="property-name-policyruleid"></a>プロパティ名: PolicyRuleId

**説明**: 一意の ID である GUID はポリシーを表し、レポートとトラブルシューティングで使用されます。

### <a name="property-name-includedidlist"></a>プロパティ名: IncludedIdList

**説明**: ポリシーが適用されるグループ。 複数のグループが追加されている場合、ポリシーは、すべてのグループ内の任意のメディアに適用されます。

**オプション** このインスタンスでは、グループ ID/GUID を使用する必要があります。

次の例は、GroupID の使用法を示しています。

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

### <a name="property-name-excludedidlist"></a>プロパティ名: ExcludedIDList

**説明**: ポリシーが適用されないグループ。

**オプション**: このインスタンスでは、グループ ID/GUID を使用する必要があります。

### <a name="property-name-entry-id"></a>プロパティ名: エントリ ID

**説明**: 1 つの PolicyRule に複数のエントリを指定できます。一意の GUID を持つ各エントリは、デバイスコントロールに 1 つの制限を指示します。

### <a name="property-name-type"></a>プロパティ名: Type

**説明**: IncludedIDList のリムーバブル 記憶域グループのアクションを定義します。

- 適用: 許可または拒否
- 監査: AuditAllowed または AuditDenied

**オプション**:

- 許可
- 拒否
- AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します。
- AuditDenied: アクセスが拒否された場合の通知とイベントを定義します。は、Deny エントリと共 **に動作する必要** があります。

同じメディアに対して競合の種類がある場合、システムはポリシーの最初のメディアを適用します。 競合の種類の例として、[許可] と **[拒否]** **があります**。

### <a name="property-name-options"></a>プロパティ名: オプション

**説明**: 通知を表示するかどうかを定義します。

:::image type="content" source="images/device-status.png" alt-text="デバイスの状態を確認できる画面":::

**オプション**: 0 ~ 4。

[許可] **または [拒否]** **の種類** が選択されている場合:

- 0: 何も
- 4: この **エントリに対して AuditAllowed** と **AuditDenied を** 無効にします。 ブロックが **発生** し **、AuditDenied** が構成されている場合でも、システムは通知を表示されません。

Type **AuditAllowed または** **AuditDenied が** 選択されている場合:

- 0: 何も
- 1: 通知の表示、AuditDenied でのみ動作
- 2: 送信イベント
- 3: 通知を表示し、イベントを送信します。 AuditAllowed にこれを適用すると、レポートのイベントだけが発生しますが、通知は表示されません。

### <a name="property-name-sid"></a>プロパティ名: Sid

**説明**: このポリシーを特定のユーザー またはユーザー グループに適用するかどうかを定義します。1 つのエントリに最大 1 つの SID を設定し、SID を使用しないエントリは、コンピューター上にポリシーを適用する方法を意味します。

### <a name="property-name-computersid"></a>プロパティ名: ComputerSid

**説明**: このポリシーを特定のコンピューターまたはコンピューター グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの ComputerSID を指定し、ComputerSID を使用しないエントリは、コンピューター上にポリシーを適用する方法を意味します。 特定のユーザーと特定のコンピューターにエントリを適用する場合は、SID と ComputerSID の両方を同じエントリに追加します。

### <a name="property-name-accessmask"></a>プロパティ名: AccessMask

**説明**: アクセスを定義します。

オプション 1 ~ 7:

- 1: 読み取り
- 2: 書き込み
- 3: 読み取りおよび書き込み
- 4: 実行
- 5: 読み取りおよび実行
- 6: 書き込みと実行
- 7: 読み取りおよび書き込みと実行

## <a name="common-removable-storage-access-control-scenarios"></a>一般的なリムーバブル Storage アクセス制御のシナリオ

Microsoft Defender for Endpoint Removable Storageアクセス制御について理解するために、一般的なシナリオをまとめました。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>シナリオ 1: すべてのユーザーへの書き込みおよび実行アクセスを防止するが、特定の承認済み USB を許可する

1. グループを作成する
    1. グループ 1: リムーバブル 記憶域と CD/DVD。 リムーバブル ストレージと CD/DVD の例として、グループ **9b28fae8-72f7-4267-a1a5-685f747a7146** のサンプル (Any Removable Storage および [CD-DVD Group.xmlファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)) があります。
    2. グループ 2: デバイスのプロパティに基づく承認済み USB。 この使用例の例は、サンプル承認済み [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのインスタンス ID - グループ **65fa649a-a111-4912-9294-fb6337a25038** です。

    > [!NOTE]
    > 値に置き `&` 換 `&amp;` える必要があります。

2. ポリシーの作成
    1. ポリシー 1: 書き込みおよび実行アクセスをブロックしますが、承認済みの USB を許可します。 この使用例の例は、シナリオ [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ブロック書き込みおよび実行アクセスのサンプルの PolicyRule **c544a991-5786-4402-9402-a032cb790d0e** ですが、承認された USBs.xmlファイルを許可します。
    2. ポリシー 2: 許可された USB への書き込みおよび実行アクセスを監査します。 この使用例の例として、PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** (シナリオ [1 監査](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 書き込みおよび承認済み USBs.xmlファイルへのアクセスの実行) があります。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>シナリオ 2: 特定の承認されていない USB をブロックするを含むすべてのユーザーへの書き込みおよび実行アクセスを監査する

1. グループを作成する
    1. グループ 1: リムーバブル 記憶域と CD/DVD。 この使用例の例は、サンプル Any Removable Storage および [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** です。
    2. グループ 2: サンプルの未承認の USB Group.xmlファイルのデバイス プロパティに基づく未承認 [の USB(](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ベンダー ID/製品 ID、フレンドリー名 – グループ **65fa649a-a111-4912-9294-fb6337a25038** など)。

    > [!NOTE]
    > 値に置き `&` 換 `&amp;` える必要があります。

2. ポリシーの作成
    1. ポリシー 1: 特定の承認されていない USB をブロックする権限を持つすべてのユーザーに対する書き込みおよび実行アクセスをブロックします。 この使用例の例として、PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** のサンプルシナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to all but block specific 未承認の USBs.xmlファイルがあります。
    2. ポリシー 2: 他のユーザーへの書き込みおよび実行アクセスを監査します。 この使用例の例は、「シナリオ [2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to others.xmlfile」の PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** です。

## <a name="deploying-and-managing-policy-via-group-policy"></a>グループ ポリシーによるポリシーの展開と管理

リムーバブル アクセスStorage機能を使用すると、グループ ポリシー経由でユーザーまたはデバイス、または両方にポリシーを適用できます。

### <a name="licensing"></a>ライセンス

リムーバブル アクセス制御の使用を開始するStorage、サブスクリプションを確認 [するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 リムーバブル アクセス制御にアクセスして使用Storageするには、リムーバブル アクセスコントロールまたはMicrosoft 365 E3必要Microsoft 365 E5。

### <a name="deploying-policy-via-group-policy"></a>グループ ポリシーによるポリシーの展開

1. すべてのグループを 1 つの `<Groups>` `</Groups>` xml ファイルに結合します。

    次の図は、シナリオ 1: 書き込みおよび実行アクセスを許可するが、特定の承認済み USB を許可するの例 [を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイスで特定の承認済み USB を許可する構成設定を表示する画面":::

2. すべてのルールを 1 つの `<PolicyRules>` `</PolicyRules>` xml ファイルに結合します。

    特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。 ポリシー Entry に SID がない場合、エントリはコンピューターのすべてのログイン インスタンスに適用されます。

    次の図は、SID プロパティの使用法を示しています。シナリオ [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)書き込みおよび実行のアクセスをすべて防ぐが、特定の承認済み USB を許可する例を示します。

    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用法を示すコードを表示する画面":::

3. ルールとグループ XML ファイルの両方をネットワーク共有フォルダーに保存し、ネットワーク共有フォルダー パスを [グループ ポリシー] 設定に格納します。[コンピューター構成管理テンプレート] Windows \>  \> **Components** \> **Microsoft Defender ウイルス対策** \> Device Control : 'デバイス制御ポリシー グループの定義' と [デバイス制御ポリシー ルールの定義] です。

   グループ ポリシーでポリシー構成 UX が見つからない場合は、[Raw] を選択してから [名前を付けて保存] を選択して [、WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml)ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx)ファイルを **ダウンロードできます**。

   - ポリシーを持つには、ターゲット コンピューターがネットワーク共有にアクセスできる必要があります。 ただし、ポリシーを読み取った後は、コンピューターの再起動後も、ネットワーク共有接続は不要になります。

    :::image type="content" source="images/device-control.png" alt-text="[デバイス制御] 画面":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Intune OMA-URI によるポリシーの展開と管理

リムーバブル アクセスStorage機能を使用すると、OMA-URI を介してユーザーまたはデバイス、または両方にポリシーを適用できます。

### <a name="licensing-requirements"></a>ライセンスの要件

リムーバブル アクセス制御の使用を開始するStorage、サブスクリプションを確認 [するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 リムーバブル アクセス制御にアクセスして使用Storageするには、リムーバブル アクセスコントロールまたはMicrosoft 365 E3必要Microsoft 365 E5。

### <a name="permission"></a>アクセス許可

Intune でのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。 カスタム ロールを作成するか、これらのアクセス許可を持つ組み込みロールを使用できます。

- ポリシーとプロファイル マネージャーの役割
- デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール
- 全体管理者

### <a name="deploying-policy-via-oma-uri"></a>OMA-URI によるポリシーの展開

**Microsoft エンドポイント マネージャー 管理センター ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 以降 & プロファイル: Custom**

1. グループごとに、OMA-URI ルールを作成します。
    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      たとえば、サンプル **内のリムーバブル 記憶域と CD/DVD** グループの場合、リンクは次のようになります。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - データ型: 文字列 (XML ファイル)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING データ型の xml ファイル":::

2. ポリシーごとに、OMA-URI も作成します。
    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData`

      たとえば、ブロック書き込みおよび実行アクセスの場合、サンプルで承認 **された USB** ルールを許可するには、次のリンクが必要です。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - データ型: 文字列 (XML ファイル)

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Intune ユーザー インターフェイスを使用したポリシーの展開と管理

この機能 (Microsoft エンドポイント マネージャー 管理センター ( ) デバイス構成プロファイル プロファイル プロファイルプラットフォームの作成: Windows 10 以降の & <https://endpoint.microsoft.com/> \> \> \> \> プロファイル: Device Control) はまだ使用できません。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint Storageデバイス コントロールリムーバブル アクセス制御データを表示する

セキュリティ ポータルMicrosoft 365、Device Control リムーバブル アクセス制御によってブロックされたリムーバブル ストレージStorage表示されます。 セキュリティにアクセスするにはMicrosoft 365サブスクリプションが必要です。

- Microsoft 365 E5 レポートの詳細

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot;
| extend parsed=parse_json(AdditionalFields)
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess) 
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict) 
| extend MediaBusType = tostring(parsed.BusType) 
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId)
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy) 
| extend MediaProductId = tostring(parsed.ProductId) 
| extend MediaVendorId = tostring(parsed.VendorId) 
| extend MediaSerialNumber = tostring(parsed.SerialNumber) 
| extend MediaVolume = tostring(parsed.Volume) 
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="リムーバブル 記憶域のブロックを示す画面":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>USB の最大数に対するリムーバブル 記憶域メディアの制限は何ですか?

100,000 メディアを持つ 1 つの USB グループ (最大 7 MB のサイズ) を検証しました。 このポリシーは、パフォーマンスの問題なく Intune と GPO の両方で動作します。

### <a name="why-does-the-policy-not-work"></a>ポリシーが機能しない理由

最も一般的な理由は、必要なマルウェア [対策クライアントのバージョンがない場合です](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。

もう 1 つの理由は、XML ファイルの "&" 文字に適切なマークダウン書式を使用しないなど、XML ファイルが正しく書式設定されていないか、テキスト エディターがファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBF を追加し、XML 解析が機能しないことです。 1 つの簡単な解決策は、サンプル ファイルを [ダウンロード](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) することです **([Raw]** を選択 **し、[名前** を付けて保存] を選択して) 更新します。

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>グループ ポリシーに [デバイス制御ポリシー グループの定義] と [デバイス制御ポリシー ルールの定義] の構成 UX はありません。

グループ ポリシー構成 UX のバックポートは行いますが [、WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルで [Raw] と [名前を付けて保存] をクリックすると、関連する adml ファイルと admx ファイルを取得できます。

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>組織で最新のマルウェア対策クライアント バージョンを使用しているコンピューターを確認する方法

次のクエリを使用して、セキュリティ ポータルでマルウェア対策クライアントのMicrosoft 365できます。

```kusto
//check the antimalware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```
