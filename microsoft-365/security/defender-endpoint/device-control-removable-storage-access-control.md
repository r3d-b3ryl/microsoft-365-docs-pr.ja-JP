---
title: Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御、リムーバブル ストレージ メディア
description: Microsoft Defender for Endpoint の概要
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
ms.openlocfilehash: cd1588221d8058963e49013df06c238b2f4a72b0
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776934"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control リムーバブル Storage アクセス制御

> [!NOTE]
> この製品のグループ ポリシー管理は、一般的に有効です (4.18.2106): [「Tech Community ブログ: Microsoft Defender for Endpoint](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806)でリムーバブル ストレージとプリンターを保護する」を参照してください。 


Microsoft Defender for Endpoint Device Control リムーバブル Storageアクセス制御を使用すると、次のタスクを実行できます。

- 除外の付いたリムーバブル 記憶域への読み取り、書き込み、または実行アクセスの監査、許可、または防止

<br/><br/>

|特権|アクセス許可|
|---|---|
|Access|読み取り、書き込み、実行|
|アクション モード|監査、許可、防止|
|CSP サポート|はい|
|GPO サポート|必要|
|ユーザー ベースのサポート|必要|
|コンピューター ベースのサポート|はい|

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

マルウェア対策クライアント Storage **4.18.2103.3** 以降の Windows 10 デバイスにリムーバブル アクセス制御を展開します。

- **4.18.2104** 以降: SerialNumberId の追加、VID_PID、ファイルパス ベースの GPO のサポート、ComputerSid
- **4.18.2105** 以降 : HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートの追加、特定のコンピューター上の特定のユーザーの組み合わせ、削除可能な SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート
- **4.18.2107** 以降: ポータブル デバイス (WPD) Windows (タブレットなどのモバイル デバイス) のサポートを追加します。高度な検索に AccountName [を追加する](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス。":::

> [!NOTE]
> リムーバブル アクセスWindows セキュリティ状態とは別にリムーバブル アクセス制御を実行Storage、すべてのコンポーネントをアクティブWindows セキュリティ必要があります。

## <a name="policy-properties"></a>ポリシーのプロパティ

次のプロパティを使用して、リムーバブル 記憶域グループを作成できます。

> [!NOTE]
> XML コメント表記を使用するコメントは、Rule および Group XML ファイルで使用できますが、XML ファイルの最初の行ではなく、最初の XML タグ内にある `<!-- COMMENT -->` 必要があります。

### <a name="removable-storage-group"></a>リムーバブル Storage グループ

<br/><br/>

|プロパティ名|説明|オプション|
|---|---|---|
|**GroupId**|[GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)は、一意の ID で、グループを表し、ポリシーで使用されます。||
|**DescriptorIdList**|グループでカバーするデバイス のプロパティを一覧表示します。 各デバイス プロパティの詳細については [、「Device Properties」](device-control-removable-storage-protection.md) を参照してください。 すべてのプロパティでは大文字と小文字が区別されます。 |<ul><li>**PrimaryId**: RemovableMediaDevices、CdRomDevices、WpdDevices</li><li>**DeviceId**</li><li>**HardwareId**</li><li>**InstancePathId**: InstancePathId は、たとえば、システム内のデバイスを一意に識別する文字列です `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0` 。 末尾の番号 (たとえば、&0) は使用可能なスロットを表し、デバイス間で変更される場合があります。 最適な結果を得る場合は、末尾にワイルドカードを使用します。 たとえば、`USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*` などです。</li><li>**FriendlyNameId**</li><li>**SerialNumberId**</li><li>**VID**</li><li>**PID**</li><li>**VID_PID**<ul><li>0751_55E0: この完全な VID/PID ペアと一致する</li><li>55E0: PID=55E0 で任意のメディアと一致する </li><li>0751: 任意のメディアを VID=0751 と一致する</li></ul></li></ul>|
|**MatchType**|DescriptorIDList で複数のデバイス プロパティが使用されている場合、MatchType はリレーションシップを定義します。|**MatchAll**: DescriptorIdList の下の属性は **And** リレーションシップです。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、システムは USB が両方の値を満たするかどうかを確認します。 <p> **MatchAny**: DescriptorIdList の下の属性は **Or リレーションシップ** です。たとえば、管理者が DeviceID と InstancePathID を置く場合、接続されている USB ごとに、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは強制を実行します。 |

### <a name="access-control-policy"></a>アクセス制御ポリシー

<br/><br/>

| プロパティ名 | 説明 | オプション |
|---|---|---|
| **PolicyRuleId** | [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier)は、一意の ID であり、ポリシーを表し、レポートとトラブルシューティングで使用されます。 | |
| **IncludedIdList** | ポリシーが適用されるグループ。 複数のグループが追加されている場合、ポリシーは、すべてのグループ内の任意のメディアに適用されます。|このインスタンスでは、グループ ID/GUID を使用する必要があります。 <p> 次の例は、GroupID の使用法を示しています。 <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | ポリシーが適用されないグループ。 | このインスタンスでは、グループ ID/GUID を使用する必要があります。 |
| **エントリ ID** | 1 つの PolicyRule には複数のエントリを指定できます。一意の GUID を持つ各エントリは、デバイスコントロールに 1 つの制限を指示します。| |
| **種類** | IncludedIDList のリムーバブル 記憶域グループのアクションを定義します。 <ul><li>適用: 許可または拒否 </li><li>監査: AuditAllowed または AuditDenied</ul></li> | <ul><li>許可</li><li>拒否 </li><li>AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します。</li><li>AuditDenied: アクセスが拒否された場合の通知とイベントを定義します。は、Deny エントリと共 **に動作する必要** があります。</li></ul> <p> 同じメディアに対して競合の種類がある場合、システムはポリシーの最初のメディアを適用します。 競合の種類の例として、[許可] と **[拒否]** **があります**。 |
| **Sid** | ローカル コンピューター Sid または AD オブジェクトの Sid は、このポリシーを特定のユーザー またはユーザー グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの Sid を含め、Sid を使用しないエントリは、コンピューター上にポリシーを適用する方法を意味します。 |  |
| **ComputerSid** | ローカル コンピューター Sid または AD オブジェクトの Sid は、このポリシーを特定のコンピューターまたはコンピューター グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの ComputerSid を指定し、ComputerSid を使用しないエントリはコンピューター上にポリシーを適用します。 特定のユーザーと特定のコンピューターにエントリを適用する場合は、Sid と ComputerSid の両方を同じエントリに追加します。 |  |
| **オプション** | 通知を表示するかどうかを定義します。 |**0-4**: [許可] または [拒否] の種類が選択されている場合。 <ul><li>0: 何も</li><li>4: この **エントリに対して AuditAllowed** と **AuditDenied を** 無効にします。 ブロックが **発生** し、AuditDenied が構成されている場合でも、システムは通知を表示されません。 </li></ul> <p> Type **AuditAllowed または** **AuditDenied が** 選択されている場合: <ul><li>0: 何も</li><li>1: 通知を表示する</li><li>2: 送信イベント</li><li>3: 通知を表示し、イベントを送信する </li></ul>|
|AccessMask|アクセスを定義します。 | **1~7**: <ol><li>読み取り</li><li>書き込み</li><li>読み取りと書き込み</li><li>実行</li><li>読み取りおよび実行</li><li>書き込みと実行 </li><li>読み取りおよび書き込みおよび実行</li></ol> |

## <a name="common-removable-storage-access-control-scenarios"></a>一般的なリムーバブル Storage アクセス制御のシナリオ

Microsoft Defender for Endpoint Removable Storageアクセス制御について理解するために、一般的なシナリオをまとめました。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>シナリオ 1: すべてのユーザーへの書き込みおよび実行アクセスを防止するが、特定の承認済み USB を許可する

1. グループを作成する

    1. グループ 1: リムーバブル 記憶域と CD/DVD。 リムーバブル ストレージと CD/DVD の例として、グループ **9b28fae8-72f7-4267-a1a5-685f747a7146** のサンプル (Any Removable Storage および [CD-DVD Group.xmlファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)) があります。
    2. グループ 2: デバイスのプロパティに基づく承認済み USB。 この使用例の例は、サンプル承認済み [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのインスタンス ID - グループ **65fa649a-a111-4912-9294-fb6337a25038** です。

    > [!TIP]
    > 値 `&` で `&amp;` 置き換える。

2. ポリシーの作成

    1. ポリシー 1: 書き込みおよび実行アクセスをブロックしますが、承認済みの USB を許可します。 この使用例の例は、シナリオ [1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ブロック書き込みおよび実行アクセスのサンプルの PolicyRule **c544a991-5786-4402-9402-a032cb790d0e** ですが、承認された USBs.xmlファイルを許可します。
    2. ポリシー 2: 許可された USB への書き込みおよび実行アクセスを監査します。 この使用例の例として、PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** (シナリオ [1 監査](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 書き込みおよび承認済み USBs.xmlファイルへのアクセスの実行) があります。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>シナリオ 2: 特定の承認されていない USB をブロックするを含むすべてのユーザーへの書き込みおよび実行アクセスを監査する

1. グループを作成する

    1. グループ 1: リムーバブル 記憶域と CD/DVD。 この使用例の例は、サンプル Any Removable Storage および [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** です。
    2. グループ 2: サンプルの未承認の USB Group.xmlファイルのデバイス プロパティに基づく未承認 [の USB(](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)ベンダー ID/製品 ID、フレンドリー名 – グループ **65fa649a-a111-4912-9294-fb6337a25038** など)。

    > [!TIP]
    > 値 `&` で `&amp;` 置き換える。

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

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイス上の特定の承認済み USB を許可する構成設定を表示する画面。":::

2. すべてのルールを 1 つの `<PolicyRules>` `</PolicyRules>` xml ファイルに結合します。

    特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。 ポリシー Entry に SID がない場合、エントリはコンピューターのすべてのログイン インスタンスに適用されます。

    次の図は、SID プロパティの使用法を示しています。シナリオ [1:](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)書き込みおよび実行のアクセスをすべて防ぐが、特定の承認済み USB を許可する例を示します。

    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用法を示すコードを表示する画面。":::

3. ルールとグループ XML ファイルの両方をネットワーク共有フォルダーに保存し、ネットワーク共有フォルダー パスを [グループ ポリシー] 設定に入 **れる:コンピューター** 構成管理用テンプレート Windows \> **Components** Microsoft Defender ウイルス対策 Device \>  \>  \> **Control**: **'Define** device control policy groups' and **'Define device control policy rules'**.

   グループ ポリシーでポリシー構成 UX が見つからない場合は、[Raw] を選択してから [名前を付けて保存] を選択して [、WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml)ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx)ファイルを **ダウンロードできます**。

   - ポリシーを持つには、ターゲット コンピューターがネットワーク共有にアクセスできる必要があります。 ただし、ポリシーを読み取った後は、コンピューターの再起動後も、ネットワーク共有接続は不要になります。

    :::image type="content" source="images/device-control.png" alt-text="[デバイスの制御] 画面。":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Intune OMA-URI によるポリシーの展開と管理

リムーバブル アクセスStorage機能を使用すると、OMA-URI を介してユーザーまたはデバイス、または両方にポリシーを適用できます。

### <a name="licensing-requirements"></a>ライセンスの要件

リムーバブル アクセス制御の使用を開始するStorage、サブスクリプションを確認 [するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 リムーバブル アクセス制御にアクセスして使用Storageするには、リムーバブル アクセスコントロールまたはMicrosoft 365 E3必要Microsoft 365 E5。

### <a name="permission"></a>アクセス許可

Intune でのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに必要です。 カスタム ロールを作成するか、これらのアクセス許可を持つ組み込みロールを使用できます。

- ポリシーとプロファイル マネージャーの役割
- デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール
- グローバル管理者

### <a name="deploying-policy-via-oma-uri"></a>OMA-URI によるポリシーの展開

Microsoft エンドポイント マネージャー センター ( ) デバイス構成プロファイル プロファイル <https://endpoint.microsoft.com/> \>  \>  \> **の** 作成 \> **プロファイル プラットフォーム: Windows 10以降&プロファイル: Custom**

1. グループごとに、OMA-URI ルールを作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      たとえば、サンプル **内のリムーバブル 記憶域と CD/DVD** グループの場合、リンクは次のようになります。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - データ型: 文字列 (XML ファイル)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="STRING データ型の xml ファイル。":::

2. ポリシーごとに、OMA-URI も作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      たとえば、ブロック書き込みおよび実行アクセスの場合、サンプルで承認 **された USB** ルールを許可するには、次のリンクが必要です。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - データ型: 文字列 (XML ファイル)

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Intune ユーザー インターフェイスを使用したポリシーの展開と管理

この機能 (Microsoft エンドポイント マネージャー 管理センター ( ) デバイス構成プロファイル プロファイル プロファイルプラットフォームの作成: Windows 10 以降の & <https://endpoint.microsoft.com/> \> \> \> \> プロファイル: Device Control) はまだ使用できません。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint Storageデバイス コントロールリムーバブル アクセス制御データを表示する

[[Microsoft 365 Defender] ポータルには、](https://security.microsoft.com/advanced-hunting)デバイスコントロールのリムーバブル アクセス制御によってトリガー Storage表示されます。 セキュリティにアクセスするにはMicrosoft 365サブスクリプションが必要です。

- Microsoft 365 E5 レポートの詳細

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
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
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="リムーバブル 記憶域のブロックを示す画面。":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>USB の最大数に対するリムーバブル 記憶域メディアの制限は何ですか?

100,000 メディアを持つ 1 つの USB グループ (最大 7 MB のサイズ) を検証しました。 このポリシーは、パフォーマンスの問題なく Intune と GPO の両方で動作します。

### <a name="why-does-the-policy-not-work"></a>ポリシーが機能しない理由

最も一般的な理由は、必要なマルウェア [対策クライアントのバージョンがない場合です](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。

もう 1 つの理由は、XML ファイルの "&" 文字に適切なマークダウン書式を使用しないなど、XML ファイルが正しく書式設定されていないか、テキスト エディターがファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBF を追加し、XML 解析が機能しないことです。 1 つの簡単な解決策は、サンプル ファイルを [ダウンロード](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) することです **([Raw]** を選択 **し、[名前** を付けて保存] を選択して) 更新します。

グループ ポリシーを使用してポリシーを展開および管理する場合は、PolicyRule と呼ばれる親ノード内の 1 つの XML ファイルに、PolicyRule とすべてのグループをグループと呼ばれる親ノード内の 1 つの XML ファイルに必ず組み合わせてください。Intune で管理する場合は、PolicyRule 1 つの XML ファイル、同じもの、1 つのグループ 1 XML ファイルを保持します。

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>グループ ポリシーに [デバイス制御ポリシー グループの定義] と [デバイス制御ポリシー ルールの定義] の構成 UX はありません。

グループ ポリシー構成 UX はバックポートしないが [、WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルで [Raw] と [名前を付けて保存] をクリックすると、関連する adml ファイルと admx ファイルを取得できます。

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
