---
title: Microsoft Defender for Endpoint Device Control リムーバブル ストレージ Access Control、リムーバブル ストレージ メディア
description: Microsoft Defender for Endpointに関するウォークスルー
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.date: 06/24/2022
ms.openlocfilehash: d9ff97aa50a03c1a75f073328a250a9acc3faf54
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490755"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control リムーバブル ストレージ Access Control

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> この製品のグループ ポリシー管理と Intune OMA-URI/Custom Policy management は一般公開されました (4.18.2106): [Tech Community ブログ: Microsoft Defender for Endpointを使用してリムーバブル ストレージとプリンターを保護します](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806)。

## <a name="device-control-removable-storage-access-control-overview"></a>Device Control リムーバブル ストレージ Access Controlの概要

デバイス制御リムーバブル ストレージAccess Control機能Microsoft Defender for Endpoint、除外の有無にかかわらず、リムーバブル ストレージへの読み取り、書き込み、または実行アクセスを監査、許可、または禁止できます。

|特権|アクセス許可|
|---|---|
|Access|読み取り、書き込み、実行|
|アクション モード|監査、許可、禁止|
|CSP サポート|はい|
|GPO のサポート|はい|
|ユーザー ベースのサポート|はい|
|マシンベースのサポート|はい|

デバイスコントロールリムーバブル ストレージAccess Control機能Microsoft Defender for Endpoint、次の機能が提供されます。

|機能|説明|Intuneを使用してデプロイする|グループ ポリシーを使用してデプロイする|
|---|---|---|---|
|リムーバブル メディア グループの作成|再利用可能なリムーバブル メディア グループを作成できます|セクションの手順 4 と 6、[Intune OMA-URI を使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-intune-oma-uri)| 「[グループ ポリシーを使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-group-policy)」セクションの手順 4 と 6|
|ポリシーの作成|各リムーバブル メディア グループを適用するポリシーを作成できます|セクション「Intune [OMA-URI を使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-intune-oma-uri)」セクションの手順 5 と 7| 「[グループ ポリシーを使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-group-policy)」セクションの手順 5 と 7|
|既定の適用|ポリシーがない場合は、リムーバブル メディアに既定のアクセス (拒否または許可) を設定できます|セクションの手順 2. [Intune OMA-URI を使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-intune-oma-uri) | セクションの手順 2. [グループ ポリシーを使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-group-policy)|
|リムーバブル ストレージ Access Controlを有効または無効にする|[無効] を設定すると、このマシンのリムーバブル ストレージ Access Control ポリシーが無効になります| セクションの手順 1. [Intune OMA-URI を使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-intune-oma-uri)| セクションの手順 1. [グループ ポリシーを使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-group-policy)|
|ファイル情報をキャプチャする|書き込みアクセスが発生したときにファイル情報をキャプチャするポリシーを作成できます|  | セクション「[グループ ポリシーを使用したリムーバブル ストレージ Access Controlの展開](#deploying-removable-storage-access-control-by-using-group-policy)」の手順 10 |

### <a name="prepare-your-endpoints"></a>エンドポイントを準備する

マルウェア対策クライアント バージョン **4.18.2103.3 以降** のWindows 10およびWindows 11 デバイスにリムーバブル ストレージ Access Controlを展開します。

- **4.18.2104 以降**: 追加 `SerialNumberId`、 `VID_PID`filepath ベースの GPO サポート、および `ComputerSid`

- **4.18.2105 以降**: ワイルドカード サポート `HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId`を追加します。特定のマシン上の特定のユーザーの組み合わせ、リムーバブル SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート

- **4.18.2107 以降**: Windows ポータブル デバイス (WPD) のサポート (タブレットなどのモバイル デバイスの場合) を追加します。[高度なハンティング](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)に追加する`AccountName`

- **4.18.2205 以降**: 既定の適用を **[プリンター**] に展開します。 **[拒否]** に設定すると、プリンターもブロックされるため、記憶域のみを管理する場合は、プリンターを許可するカスタム ポリシーを作成してください。

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス" lightbox="images/powershell.png":::

> [!NOTE]
> Windows セキュリティ状態に関係なくリムーバブル ストレージ Access Controlを実行できるため、Windows セキュリティ コンポーネントをアクティブにする必要はありません。

## <a name="device-control-removable-storage-access-control-policies"></a>Device Control リムーバブル ストレージ Access Control ポリシー

次のプロパティを使用して、リムーバブル ストレージ グループを作成できます。

> [!NOTE]
> XML コメント表記 `<!-- COMMENT -->` を使用するコメントは、ルールおよびグループ XML ファイルで使用できますが、XML ファイルの最初の行ではなく、最初の XML タグ内にある必要があります。

### <a name="removable-storage-group"></a>リムーバブル ストレージ グループ

|プロパティ名|説明|オプション|
|---|---|---|
|**GroupId**|一意の ID である GUID はグループを表し、ポリシーで使用されます。||
|**DescriptorIdList**|グループ内でカバーするために使用するデバイス プロパティを一覧表示します。 各デバイス プロパティの詳細については、 [デバイスのプロパティ](device-control-removable-storage-protection.md) に関するページを参照してください。 すべてのプロパティで大文字と小文字が区別されます。 |**PrimaryId**: `RemovableMediaDevices`, , `CdRomDevices``WpdDevices`<p>**BusId**: たとえば、USB、SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**: InstancePathId は、たとえば、システム `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`内のデバイスを一意に識別する文字列です。 末尾の数値 (&0 など) は使用可能なスロットを表し、デバイスからデバイスに変更される場合があります。 最適な結果を得るには、最後にワイルドカードを使用します。 たとえば、「 `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*` 」のように入力します。<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: この正確な VID/PID ペアと一致する<p>`_55E0`: PID=55E0 の任意のメディアと一致する <p>`0751_`: VID=0751 で任意のメディアと一致する|
|**MatchType**|複数のデバイス プロパティが使用されている場合は、 `DescriptorIDList`MatchType によってリレーションシップが定義されます。|**MatchAll**: 次の属性`DescriptorIdList`は **And** リレーションシップになります。たとえば、管理者が接続されているすべての USB に対して`InstancePathID`、USB `DeviceID` が両方の値を満たしているかどうかを確認します。 <p> **MatchAny**: DescriptorIdList の下の属性は **Or** リレーションシップになります。たとえば、管理者 `DeviceID` が接続されているすべての USB に対して `InstancePathID`、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは適用を行います。|

### <a name="access-control-policy"></a>Access Control ポリシー
次のプロパティを使用して、アクセス制御ポリシーを作成できます。

| プロパティ名 | 説明 | オプション |
|---|---|---|
| **PolicyRule Id** | 一意の ID である GUID はポリシーを表し、レポートとトラブルシューティングで使用されます。 | |
| **IncludedIdList** | ポリシーが適用されるグループ。 複数のグループが追加されている場合、ポリシーはすべてのグループ内の任意のメディアに適用されます。|このインスタンスでは、グループ ID/GUID を使用する必要があります。 <p> 次の例は、GroupID の使用方法を示しています。 <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | ポリシーが適用されないグループ。 | このインスタンスでは、グループ ID/GUID を使用する必要があります。 |
| **エントリ ID** | 1 つの PolicyRule に複数のエントリを含めることができます。一意の GUID を持つ各エントリは、Device Control に 1 つの制限を指示します。| |
| **型** | IncludedIDList でリムーバブル ストレージ グループのアクションを定義します。 <p>適用: 許可または拒否 <p>監査: AuditAllowed または AuditDenied<p> | 許可<p>拒否 <p>AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します <p>AuditDenied: アクセスが拒否されたときに通知とイベントを定義します。は **Deny エントリと** 連携する必要があります。<p> 同じメディアに競合の種類がある場合、システムはポリシーの最初のメディアを適用します。 競合の種類の例として **、[許可]** と **[拒否] があります**。 |
| **Sid** | ローカル ユーザー Sid またはユーザー Sid グループ、または AD オブジェクトの Sid は、特定のユーザーまたはユーザー グループに対してこのポリシーを適用するかどうかを定義します。1 つのエントリに最大 1 つの Sid を指定でき、Sid のないエントリは、マシンにポリシーを適用することを意味します。 |  |
| **ComputerSid** | ローカル コンピューター Sid またはコンピューター Sid グループ、または AD オブジェクトの Sid は、特定のコンピューターまたはマシン グループに対してこのポリシーを適用するかどうかを定義します。1 つのエントリに最大 1 つの ComputerSid を指定でき、ComputerSid のないエントリは、コンピューターにポリシーを適用することを意味します。 特定のユーザーと特定のコンピューターにエントリを適用する場合は、Sid と ComputerSid の両方を同じエントリに追加します。 |  |
| **オプション** | 通知を表示するかどうかを定義します |**[型の許可] が選択されている場合**: <p>0: 何もない<p>4: このエントリ **に対して AuditAllowed** と **AuditDenied** を無効にします。 **許可** が発生し、AuditAllowed が構成されている場合でも、システムはイベントを送信しません。 <p>8: ファイル情報をキャプチャし、書き込みアクセスの証拠としてファイルのコピーを作成します。 <p>16: 書き込みアクセスのファイル情報をキャプチャします。 <p>**[型拒否] が選択されている場合**: <p>0: 何もない<p>4: このエントリ **の AuditDenied** を無効にします。 **ブロック** が発生し、AuditDenied が構成されている場合でも、システムは通知を表示しません。 <p>**[種類 **AuditAllowed** ] が選択されている場合**: <p>0: 何もない <p>1: 何もない <p>2: イベントを送信する<p> **[種類 **AuditDenied** ] が選択されている場合**: <p>0: 何もない <p>1: 通知を表示する <p>2: イベントを送信する<p>3: 通知を表示し、イベントを送信する |
|AccessMask|アクセスを定義します。 | **ディスク レベルのアクセス**: <p>1: 読み取り <p>2: 書き込み <p>4: 実行 <p>**ファイル システム レベルのアクセス**: <p>8: ファイル システムの読み取り <p>16: ファイル システムの書き込み <p>32: ファイル システムの実行 <p><p>バイナリ OR 操作を実行すると、複数のアクセス権を持つことができます。たとえば、読み取りと書き込みと実行の AccessMask は 7 になります。読み取りと書き込みの AccessMask は 3 になります。|

## <a name="device-control-removable-storage-access-control-scenarios"></a>Device Control リムーバブル ストレージのAccess Controlシナリオ

リムーバブル ストレージ Access ControlのMicrosoft Defender for Endpoint理解を深めるために、一般的なシナリオをいくつか紹介しました。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>シナリオ 1: 特定の承認済み USB を許可する以外のすべてのユーザーへの書き込みと実行のアクセスを禁止する

1. グループを作成する

    1. グループ 1: リムーバブル ストレージと CD/DVD。 リムーバブル ストレージと CD/DVD の例として、サンプル [のリムーバブル ストレージと CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** があります。

    2. グループ 2: デバイスのプロパティに基づいて承認された USB。 このユース ケースの例として、サンプル [の承認済み USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルのインスタンス ID - グループ **65fa649a-a111-4912-9294-fb6337a25038** があります。

    > [!TIP]
    > 値に置`&amp;`き換えます`&`。

2. ポリシーの作成

    1. ポリシー 1: 書き込みと実行アクセスをブロックしますが、承認済みの USB を許可します。 このユース ケースの例として、サンプル シナリオ 1 の PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** が [書き込みと実行のアクセスをブロックしますが、承認されたUSBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルを許可します。

    2. ポリシー 2: 許可された USB への書き込みと実行のアクセスを監査します。 このユース ケースの例として、サンプル シナリオ 1 の PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** は [、承認済みのUSBs.xmlファイルへの書き込みと実行アクセスを監査することです](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>シナリオ 2: 特定の未承認の USB をブロックする以外のすべてのアクセスに対する書き込みと実行のアクセスを監査する

1. グループを作成する

    1. グループ 1: リムーバブル ストレージと CD/DVD。 このユース ケースの例として、サンプル [のリムーバブル ストレージファイルと CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** があります。

    2. グループ 2: デバイスのプロパティに基づく未承認の USB(ベンダー ID/製品 ID、フレンドリ名- グループ **65fa649a-a111-4912-9294-fb6337a25038** )、サンプル [の未承認 USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイル。

    > [!TIP]
    > 値に置`&amp;`き換えます`&`。

2. ポリシーの作成

    1. ポリシー 1: 特定の未承認の USB をブロックする以外のすべての書き込みと実行アクセスをブロックします。 このユース ケースの例は、サンプル シナリオ 2 の PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** です。ただし、 [特定の未承認のUSBs.xmlファイルへのアクセスをブロック](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) します。

    2. ポリシー 2: 他のユーザーへの書き込みと実行アクセスを監査します。 このユース ケースの例として、サンプル シナリオ 2 のサンプル シナリオ 2 の PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** が [others.xmlファイルへのアクセスを監査することです](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

## <a name="deploying-and-managing-removable-storage-access-control-by-using-intune-oma-uri"></a>Intune OMA-URI を使用したリムーバブル ストレージ Access Controlのデプロイと管理

リムーバブル ストレージ Access Control機能を使用すると、OMA-URI を使用して、ユーザーまたはデバイス、またはその両方にポリシーを適用できます。

### <a name="licensing-requirements"></a>ライセンスの要件

リムーバブル ストレージ Access Controlの使用を開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)を確認する必要があります。 リムーバブル ストレージ Access Controlにアクセスして使用するには、Microsoft 365 E3またはMicrosoft 365 E5が必要です。

### <a name="permission"></a>アクセス許可

Intuneでのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに付与されている必要があります。 カスタム ロールを作成することも、これらのアクセス許可を持つ組み込みロールを使用することもできます。

- ポリシーとプロファイル マネージャーのロール
- デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示のアクセス許可が有効になっているカスタム ロール
- グローバル管理者

### <a name="deploying-removable-storage-access-control-by-using-intune-oma-uri"></a>Intune OMA-URI を使用したリムーバブル ストレージ Access Controlのデプロイ

Microsoft エンドポイント マネージャー 管理センター (<https://endpoint.microsoft.com/>) **> デバイス>プロファイル >プラットフォームの作成: Windows 10 以降、プロファイルの種類: テンプレート>カスタム** に移動する

1. 次のようにデバイス制御を有効または無効にします。

   - [ **カスタム >構成設定**] で、[ **追加**] をクリックします。
   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **デバイス制御を有効にする****名前**
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`
     - **整数** としての **データ型**
     - **1** としての **値**

       `Disable: 0`
       `Enable: 1`

     - [**保存**] をクリックします。

   :::image type="content" source="images/enable-rsac.png" alt-text="リムーバブル ストレージ Access Control ポリシーを有効にするスクリーンショット" lightbox="images/enable-rsac.png":::

2. 既定の適用を設定する:

   すべてのデバイスコントロール機能 (, , , `PrinterDevices`) に対して既定`WpdDevices``CdRomDevices`のアクセス (`RemovableMediaDevices`拒否または許可) を設定できます。

   たとえば、 **拒否** ポリシーまたは **許可** ポリシー `RemovableMediaDevices`を使用していますが、ポリシーが設定されていない `CdRomDevices` 場合や `WpdDevices`、 . このポリシーを使用して **既定の拒否** を設定すると、読み取り/書き込み/実行アクセスが`CdRomDevices``WpdDevices`ブロックされます。 ストレージのみを管理する場合は、プリンターの **許可** ポリシーを作成してください。それ以外の場合は、この既定の適用がプリンターにも適用されます。

   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **既定の拒否** として **名前を付** けます
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`
     - **整数** としての **データ型**
     - **1** または **2** の **値**

       `DefaultEnforcementAllow = 1`
       `DefaultEnforcementDeny = 2`

     - [**保存**] をクリックします。

   :::image type="content" source="images/default-deny.png" alt-text="既定の適用を拒否として設定するスクリーンショット" lightbox="images/default-deny.png":::

3. 監査の既定の拒否:

   既定の拒否の監査ポリシーは、次のように作成できます。

   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **監査の既定の拒否** としての **名前**
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bf3520ea7-fd1b-4237-8ebc-96911db44f8e%7d/RuleData`

       :::image type="content" source="images/audit-default-deny-1.png" alt-text="既定の拒否ポリシーの監査を作成するスクリーンショット" lightbox="images/audit-default-deny-1.png":::

     - **文字列としてのデータ型** **(XML ファイル)**
     - **監査の既定のDeny.xml** ファイルとしての **カスタム XML**。

       XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20Default%20Deny.xml>

       次の XML データを使用して、既定の拒否の監査ポリシーを作成します。

       :::image type="content" source="images/audit-default-deny-xml-file-1.png" alt-text="監査の既定の拒否 xml ファイルのスクリーンショット":::

4. ReadOnly - グループ:

   次のように、ReadOnly アクセス権を持つリムーバブル ストレージ グループを作成できます。

   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **任意のリムーバブル ストレージ グループ** として **名前** を付けます
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

       :::image type="content" source="images/any-removable-storage-group.png" alt-text="リムーバブル ストレージ グループを作成するスクリーンショット" lightbox="images/any-removable-storage-group.png":::

     - **文字列としてのデータ型** **(XML ファイル)**
       - **任意のリムーバブル ストレージ、CD-DVD、WPD Group.xml** ファイルとしての **カスタム XML**

         XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml>

         次の XML データを使用して、ReadOnly アクセスを使用して '任意のリムーバブル ストレージと CD-DVD および WPD グループ' を作成します。

         :::image type="content" source="images/read-only-group-xml-file.png" alt-text="読み取り専用グループ xml ファイルのスクリーンショット":::

5. ReadOnly - ポリシー:

   ReadOnly ポリシーを作成し、それを ReadOnly リムーバブル ストレージ グループに適用して、次のように読み取りアクティビティを許可できます。

   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **読み取りを許可するアクティビティ** として **名前を付** けます
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bf7e75634-7eec-4e67-bec5-5e7750cb9e02%7d/RuleData`

       :::image type="content" source="images/allow-read-activity.png" alt-text="読み取りアクティビティを許可するポリシーのスクリーンショット" lightbox= "images/allow-read-activity.png":::

     - **文字列としてのデータ型** **(XML ファイル)**
     - **カスタム XML** as **Allow Read.xml**  ファイル

       XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20Read.xml>

       次の XML データを使用して ReadOnly ポリシーを作成し、ReadOnly リムーバブル ストレージ グループに適用します。

       :::image type="content" source="images/read-only-policy-xml-file.png" alt-text="読み取り専用ポリシー xml ファイルのスクリーンショット":::

6. 許可されたメディアのグループを作成する: 次のように、許可されたメディア グループを作成できます。
   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **承認済み USBs グループ** として **名前** を付けます
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b65fa649a-a111-4912-9294-fb6337a25038%7d/GroupData`

       :::image type="content" source="images/create-group-allowed-medias.png" alt-text="承認済み USBs グループの作成のスクリーンショット" lightbox="images/create-group-allowed-medias.png":::

     - **文字列としてのデータ型** **(XML ファイル)**
     - **カスタム XML** as **Approved USBs Group.xml** ファイル

       XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Approved%20USBs%20Group.xml>

       次の XML データを使用して、許可されるメディア グループを作成します。

       :::image type="content" source="images/create-group-allowed-medias-xml-file.png" alt-text="許可されたメディア xml ファイルのグループを作成するスクリーンショット":::

7. 承認済みの USB グループを許可するポリシーを作成する: 次のように、承認済みの USB グループを許可するポリシーを作成できます。
   - [ **行の追加]** ウィンドウで、次のように入力します。
     - **アクセス許可と監査ファイルの情報** として **名前を付** ける
     - **OMA-URI** as `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bb2061588-029e-427d-8404-6dfec096a571%7d/RuleData`

       :::image type="content" source="images/allow-access-audit-file-information-1.png" alt-text="アクセスと監査ファイルの情報を許可するのスクリーンショット" lightbox= "images/allow-access-audit-file-information-1.png":::

     - **文字列としてのデータ型** **(XML ファイル)**
     - **カスタム XML** as **Allow full access and audit file.xml**  file

       XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20full%20access%20and%20audit%20file.xml>

       承認された USB グループを許可するポリシーを作成するには、次の XML データを使用します。

       :::image type="content" source="images/create-policy-allow-approved-usb-group-xml-intune.png" alt-text="承認済みの USB グループ XML ファイルを許可するポリシーを作成するスクリーンショット":::

       ポリシーの '47' とは何を意味しますか? 9 + 2 + 36 = 47 です。

       - 読み取りアクセス: 1 + 8 = 9。
       - 書き込みアクセス: ディスク レベル 2。
       - 実行: 4 + 32 = 36。

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Intune ユーザー インターフェイスを使用したポリシーのデプロイと管理

この機能は、Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com/>) で使用できます。 **Endpoint Security Attack** > **Surface Reduction** > **Create Policy** に移動します。 [**プラットフォーム: プロファイル:** **デバイス制御**] でWindows 10以降を選択します。

## <a name="deploying-and-managing-removable-storage-access-control-by-using-group-policy"></a>グループ ポリシーを使用したリムーバブル ストレージ Access Controlのデプロイと管理

リムーバブル 記憶域Access Control機能を使用すると、ユーザーまたはデバイス、またはその両方にグループ ポリシーを使用してポリシーを適用できます。

### <a name="licensing"></a>ライセンス

リムーバブル ストレージ Access Controlの使用を開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)を確認する必要があります。 リムーバブル ストレージ Access Controlにアクセスして使用するには、Microsoft 365 E3またはMicrosoft 365 E5が必要です。

### <a name="deploying-removable-storage-access-control-by-using-group-policy"></a>グループ ポリシーを使用したリムーバブル ストレージ Access Controlのデプロイ

1. リムーバブル ストレージ Access Controlを有効または無効にします。

   デバイス制御は、次のように有効にできます。

   - **Windows コンポーネント> Microsoft Defender ウイルス対策>機能>デバイスコントロール>コンピューター構成>管理用テンプレートに** 移動する
   - [ **デバイス制御** ] ウィンドウで、[ **有効]** を選択します。

   :::image type="content" source="images/enable-rsac-gp.png" alt-text="グループ ポリシーを使用した RSAC の有効化のスクリーンショット " lightbox="images/enable-rsac-gp.png":::

2. 既定の適用を設定する:

   すべてのデバイスコントロール機能 (RemovableMediaDevices、CdRomDevices、WpdDevices、PrinterDevices) に対して既定のアクセス (拒否または許可) を設定できます。

   たとえば、RemovableMediaDevices には拒否ポリシーまたは許可ポリシーがありますが、CdRomDevices または WpdDevices のポリシーはありません。 このポリシーを使用して既定の拒否を設定すると、CdRomDevices または WpdDevices への読み取り/書き込み/実行アクセスがブロックされます。 ストレージのみを管理する場合は、必ずプリンターの許可ポリシーを作成してください。それ以外の場合は、この既定の適用もプリンターにも適用されます。

   - **Windows コンポーネント> Microsoft Defender ウイルス対策>機能>デバイスコントロール >>管理テンプレートに移動>デバイス コントロールの既定の適用を選択** する

   - [ **デバイスコントロールの既定の適用の選択]** ウィンドウで、[ **既定の拒否**] を選択します。

   :::image type="content" source="images/set-default-enforcement-deny-gp.png" alt-text="既定の適用 = グループ ポリシーを使用して拒否を設定するスクリーンショット" lightbox="images/set-default-enforcement-deny-gp.png":::

3. 監査の既定の拒否:

   次の XML データを使用して、既定の拒否の監査ポリシーを作成します。

   :::image type="content" source="images/audit-default-deny-gp.png" alt-text="監査の既定の拒否 xml データのスクリーンショット":::

4. ReadOnly - グループ:

   次の XML データを使用して、ReadOnly アクセスを使用してリムーバブル ストレージ グループを作成します。

   :::image type="content" source="images/read-only-group-gp.png" alt-text="リムーバブル ストレージ グループ xml データの読み取り専用のスクリーン ショット":::

5. ReadOnly - ポリシー:

   次の XML データを使用して ReadOnly ポリシーを作成し、ReadOnly リムーバブル ストレージ グループに適用して読み取りアクティビティを許可します。

    :::image type="content" source="images/read-only-policy-gp.png" alt-text="読み取り専用ポリシー xml データのスクリーン ショット" lightbox="images/read-only-policy-gp.png":::

6. 許可されたメディアのグループを作成する:

   次の XML データを使用して、リムーバブル ストレージが許可されているメディア グループを作成します。

   :::image type="content" source="images/create-group-allowed-medias-gp.png" alt-text="許可されたメディアのグループを作成するための xml データのスクリーンショット" lightbox="images/create-group-allowed-medias-gp.png":::

7. 承認済みの USB グループを許可するポリシーを作成します。

   次の XML データを使用して、承認された USB グループを許可するポリシーを作成します。

   :::image type="content" source="images/create-policy-allow-approved-usb-group-xml.png" alt-text="グループ ポリシーを使用して承認された USB グループを許可するポリシーを作成する XML データのスクリーンショット" lightbox="images/create-policy-allow-approved-usb-group-xml.png":::

   ポリシーの '47' とは何を意味しますか? 9 + 2 + 36 = 47 です。

   - 読み取りアクセス: 1 + 8 = 9。
   - 書き込みアクセス: ディスク レベル 2。
   - 実行: 4 + 32 = 36。

8. グループを 1 つの XML ファイルに結合します。

   次のように、デバイス制御ポリシー グループを 1 つの XML ファイルに結合できます。

   - **[コンピューター構成** \> **管理用テンプレート** \> **] Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **デバイスコントロール定義** \> **デバイス制御ポリシー グループ** に移動します。

    :::image type="content" source="images/define-device-control-policy-grps-gp.png" alt-text="デバイス制御ポリシー グループの定義のスクリーンショット" lightbox="images/define-device-control-policy-grps-gp.png":::

   - [ **デバイス制御ポリシー グループの定義** ] ウィンドウで、XML グループ データを含むファイル パスを入力します。

     XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml>

     デバイス制御ポリシー グループの xml スキーマを次に示します。

     :::image type="content" source="images/combine-grps-xml-file-gp.png" alt-text="グループを 1 つの XML ファイルに結合するスクリーンショット":::

9. ポリシーを 1 つの XML ファイルに結合します。

   次のように、デバイス制御ポリシー規則を 1 つの XML ファイルに結合できます。

   - **Windows コンポーネント> Microsoft Defender ウイルス対策>デバイス制御>デバイス制御ルールの定義>[コンピューター構成>管理テンプレート**] に移動します

     :::image type="content" source="images/define-device-cntrl-policy-rules-gp.png" alt-text="デバイス制御ポリシー規則の定義のスクリーンショット" lightbox="images/define-device-cntrl-policy-rules-gp.png":::

   - [ **デバイス制御ポリシー規則の定義** ] ウィンドウで、[ **有効]** を選択し、XML ルール データを含むファイル パスを入力します。

     XML ファイル パス: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Policies.xml>

     デバイス制御ポリシー 規則の xml スキーマを次に示します。

    :::image type="content" source="images/combine-policies-xml-gp.png" alt-text="ポリシーを 1 つの XML ファイルに結合するスクリーンショット":::

10. ファイルのコピーの場所を設定します (証拠):

    書き込みアクセスが発生したときにファイルのコピー (証拠) を作成する場合は、システムがコピーを保存できる場所を設定する必要があります。

    - **Microsoft Defender ウイルス対策 >>デバイスコントロール> Windows コンポーネント >>管理用テンプレートに移動>、デバイスコントロールの証拠データのリモートの場所を定義** します。

    - [ **デバイス制御証拠データのリモートの場所の定義** ] ウィンドウで、[ **有効]** を選択し、ローカルまたはネットワーク共有フォルダーのパスを入力します。

      :::image type="content" source="images/evidence-data-remote-location-gp.png" alt-text="デバイスコントロールの証拠データのリモートの場所を定義するスクリーンショット" lightbox="images/evidence-data-remote-location-gp.png":::

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでデバイス コントロールのリムーバブル ストレージ Access Control データを表示する

[Microsoft 365 Defender ポータル](https://security.microsoft.com/advanced-hunting)には、Device Control リムーバブル ストレージ Access Controlによってトリガーされるイベントが表示されます。 Microsoft 365 セキュリティにアクセスするには、次のサブスクリプションが必要です。

- E5 レポート用 Microsoft 365

```kusto
//RemovableStoragePolicyTriggered: event triggered by Disk level enforcement
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
| extend parsed=parse_json(AdditionalFields)
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)
| extend MediaBusType = tostring(parsed.BusType)
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId)
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

```kusto
//information of file written to removable storage
DeviceEvents
| where ActionType contains "RemovableStorageFileEvent"
| extend parsed=parse_json(AdditionalFields)
| extend Policy = tostring(parsed.Policy)
| extend PolicyRuleId = tostring(parsed.PolicyRuleId)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaInstanceId = tostring(parsed.InstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
| extend FileInformationOperation = tostring(parsed.DuplicatedOperation)
| extend FileEvidenceLocation = tostring(parsed.TargetFileLocation)
| project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, Policy, PolicyRuleId, FileInformationOperation, MediaClassName, MediaInstanceId, MediaName, MediaProductId, MediaVendorId, MediaSerialNumber, FileName, FolderPath, FileSize, FileEvidenceLocation, AdditionalFields
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="リムーバブル ストレージのブロックを示す画面。":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>グループ ID/PolicyRule Id/Entry ID の GUID を生成する方法

オンライン オープンソースまたは PowerShell を使用して GUID を生成できます 。 [PowerShell を使用して GUID を生成する方法](/powershell/module/microsoft.powershell.utility/new-guid)

![image](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

### <a name="what-are-the-removable-storage-media-and-policy-limitations"></a>リムーバブル ストレージ メディアとポリシーの制限事項は何ですか?

Microsoft エンドポイント マネージャー管理センター (Intune) から、または Microsoft Graph APIを介してバックエンド呼び出しが行われるため、バックエンド呼び出しは OMA-URI (GET to read or PATCH to update) を介して行われるため、制限は、XML ファイル用に正式に 350,000 文字である Microsoft の任意の OMA-URI カスタム構成プロファイルと同じです。

たとえば、特定のユーザーを "許可"/"監査許可" するためにユーザー SID ごとに 2 つのエントリ ブロックが必要で、最後に "Deny" all に 2 つのエントリ ブロックが必要な場合は、2,276 人のユーザーを管理できます。

### <a name="why-does-the-policy-not-work"></a>ポリシーが機能しないのはなぜですか?

1. 最も一般的な理由は、必要な [マルウェア対策クライアント バージョン](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)がないことです。

2. もう 1 つの理由は、XML ファイルが正しく書式設定されていない、たとえば、XML ファイル内の "&" 文字に正しいマークダウン書式を使用していない場合や、テキスト エディターでファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBFが追加され、XML 解析が機能しないことです。 簡単な解決策の 1 つは、 [サンプル ファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) をダウンロードして ( **[未加工** ] を選択してから **[名前を付けて保存]** を選択して) 更新することです。

3. グループ ポリシーを使用してポリシーをデプロイおよび管理する場合は、PolicyRule という親ノード内の 1 つの XML ファイルにすべての PolicyRule を結合し、すべてのグループをグループという親ノード内の 1 つの XML ファイルに結合してください。Intuneを通じて管理する場合は、1 つの PolicyRule 1 つの XML ファイルを 1 つのグループ 1 つの XML ファイルのままにしてください。

それでも問題が解決しない場合は、管理者と cmd を実行してサポート cab を共有してください:"%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>自分のグループ ポリシーには、"デバイス制御ポリシー グループの定義" と "デバイス制御ポリシールールの定義" に対する構成 UX がありません

グループ ポリシー構成 UX はバックポートしませんが、[WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルで [未加工] と [名前を付けて保存] をクリックすると、関連する adml ファイルと admx ファイルを引き続き取得できます。

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>最新のポリシーがターゲット マシンにデプロイされているかどうかを確認するにはどうすればよいですか?

PowerShell で "Get-MpComputerStatus" を管理者として実行できます。 次の値は、ターゲット コンピューターに最新のポリシーが適用されているかどうかを示します。

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>組織内で古いマルウェア対策クライアント のバージョンを使用しているマシンを確認するにはどうすればよいですか?

次のクエリを使用して、Microsoft 365 セキュリティ ポータルでマルウェア対策クライアントのバージョンを取得できます。

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
