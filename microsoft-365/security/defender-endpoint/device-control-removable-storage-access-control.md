---
title: Microsoft Defender for Endpoint デバイス コントロール リムーバブル Storage Access Controlリムーバブル 記憶域メディア
description: 詳細については、Microsoft Defender for Endpoint
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
ms.date: 03/18/2022
ms.openlocfilehash: 3b3e01fd0d205182f7d028e2170cc00ebb6f780e
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568074"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint デバイス コントロール リムーバブル Storage Access Control

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> この製品の グループ ポリシー 管理と Intune OMA-URI/カスタム ポリシー管理が一般提供されました (4.18.2106): 「Tech [Community blog: protect](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806) your removable storage and printer with Microsoft Defender for Endpoint」を参照してください。


Microsoft Defender for Endpointコントロールリムーバブル Storage Access Controlを使用すると、次のタスクを実行できます。

- 除外の付いたリムーバブル 記憶域への読み取り、書き込み、または実行アクセスの監査、許可、または防止

|特権|アクセス許可|
|---|---|
|Access|読み取り、書き込み、実行|
|アクション モード|監査、許可、防止|
|CSP サポート|はい|
|GPO サポート|はい|
|ユーザー ベースのサポート|はい|
|コンピューター ベースのサポート|はい|

|機能|説明|サーバー経由Intune|サーバー経由グループ ポリシー|
|---|---|---|---|
|リムーバブル メディア グループの作成|再利用可能なリムーバブル メディア グループを作成できます|「OMA-URI によるポリシーの展開」[セクションの手順](#deploying-policy-via-oma-uri) 1 | セクションの手順 1, [Deploying policy via グループ ポリシー](#deploying-policy-via-group-policy)|
|ポリシーの作成|各リムーバブル メディア グループを適用するポリシーを作成できます|「OMA-URI によるポリシーの展開」[セクションの手順](#deploying-policy-via-oma-uri) 2 | 「ポリシーの展開」セクションの手順 [2 と 3](#deploying-policy-via-group-policy) を参照グループ ポリシー |
|既定の適用|ポリシーがない場合は、既定のアクセス (拒否または許可) をリムーバブル メディアに設定できます|「OMA-URI によるポリシーの[展開」セクションの手順](#deploying-policy-via-oma-uri) 3 | セクションの手順 4, [Deploying policy via グループ ポリシー](#deploying-policy-via-group-policy) |
|リムーバブル デバイスを有効または無効Storage Access Control|[無効にする] を設定すると、このコンピューターのリムーバブル Storage Access Controlポリシーが無効にされます。| 「OMA-URI によるポリシーの展開」[セクションの手順](#deploying-policy-via-oma-uri) 4 | セクションの手順 5, [Deploying policy via グループ ポリシー](#deploying-policy-via-group-policy) |
|ファイル情報のキャプチャ|書き込みアクセスが発生した場合にファイル情報をキャプチャするポリシーを作成できます| 「[OMA-URI](#deploying-policy-via-oma-uri) によるポリシーの展開」セクションの手順 2 と 5 | セクションの手順 2 と 6, [Deploying policy via グループ ポリシー](#deploying-policy-via-group-policy) |

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

マルウェア対策クライアント Storage Access Control **4.18.2103.3** 以降Windows 10デバイスおよび Windows 11 デバイスにリムーバブル デバイスを展開します。

- **4.18.2104** 以降: SerialNumberId の追加、VID_PID、ファイルパス ベースの GPO のサポート、ComputerSid

- **4.18.2105** 以降: HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートの追加、特定のコンピューター上の特定のユーザーの組み合わせ、削除可能な SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート

- **4.18.2107** 以降: Windows ポータブル デバイス (WPD) サポート (タブレットなどのモバイル デバイス用) を追加します。高度な検索に AccountName を [追加](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)する

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス" lightbox="images/powershell.png":::

> [!NOTE]
> リムーバブル コンポーネントWindows セキュリティ状態とは別にリムーバブル コンポーネントを実行Storage Access Control必要Windows セキュリティです。

## <a name="policy-properties"></a>ポリシーのプロパティ

次のプロパティを使用して、リムーバブル 記憶域グループを作成できます。

> [!NOTE]
> XML コメント表記を使用する `<!-- COMMENT -->` コメントは、Rule および Group XML ファイルで使用できますが、XML ファイルの最初の行ではなく、最初の XML タグ内にある必要があります。

### <a name="removable-storage-group"></a>リムーバブル Storage グループ

|プロパティ名|説明|オプション|
|---|---|---|
|**グループ ID**|一意の ID である GUID は、グループを表し、ポリシーで GroupId として使用されます。||
|**DescriptorIdList**|グループでカバーするデバイス のプロパティを一覧表示します。 各デバイス プロパティの詳細については、「 [Device Properties」](device-control-removable-storage-protection.md) を参照してください。 すべてのプロパティでは大文字と小文字が区別されます。 |**PrimaryId**: `RemovableMediaDevices`, `CdRomDevices``WpdDevices`<p>**BusId**: たとえば、USB、SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**: InstancePathId は、たとえば、システム内のデバイスを一意に識別する文字列です `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`。 末尾の番号 (たとえば、&0) は使用可能なスロットを表し、デバイス間で変更される場合があります。 最適な結果を得る場合は、末尾にワイルドカードを使用します。 たとえば、「 `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*` 」のように入力します。<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: この完全な VID/PID ペアと一致する<p>`_55E0`: PID=55E0 と任意のメディアを一致する <p>`0751_`: 任意のメディアを VID=0751 と一致する|
|**MatchType**|複数のデバイス プロパティが使用されている `DescriptorIDList`場合、MatchType はリレーションシップを定義します。|**MatchAll**: `DescriptorIdList` Will の下の属性は **And** `DeviceID` `InstancePathID`リレーションシップになります。たとえば、管理者が接続されている USB ごとに、USB が両方の値を満たしているかどうかをシステムがチェックします。 <p> **MatchAny**: DescriptorIdList の下の属性は **Or リレーションシップ** です。たとえば、管理者`DeviceID``InstancePathID`が接続されている USB ごとに、デバイス ID または **InstanceID** の値が同一である限り、システムは強制を **実行** します。 |

### <a name="access-control-policy"></a>Access Controlポリシー

| プロパティ名 | 説明 | オプション |
|---|---|---|
| **PolicyRule Id** | 一意の ID である GUID はポリシーを表し、レポートとトラブルシューティングで使用されます。 | |
| **IncludedIdList** | ポリシーが適用されるグループ。 複数のグループが追加されている場合、ポリシーは、すべてのグループ内の任意のメディアに適用されます。|このインスタンスでは、グループ ID/GUID を使用する必要があります。 <p> 次の例は、GroupID の使用法を示しています。 <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | ポリシーが適用されないグループ。 | このインスタンスでは、グループ ID/GUID を使用する必要があります。 |
| **エントリ ID** | 1 つの PolicyRule には複数のエントリを指定できます。一意の GUID を持つ各エントリは、デバイスコントロールに 1 つの制限を指示します。| |
| **Type** | IncludedIDList のリムーバブル 記憶域グループのアクションを定義します。 <p>適用: 許可または拒否 <p>監査: AuditAllowed または AuditDenied<p> | 許可<p>拒否 <p>AuditAllowed: アクセスが許可されている場合の通知とイベントを定義します。 <p>AuditDenied: アクセスが拒否された場合の通知とイベントを定義します。は、Deny エントリと共 **に動作する必要** があります。<p> 同じメディアに対して競合の種類がある場合、システムはポリシーの最初のメディアを適用します。 競合の種類の例として、[許可] と **[拒否]** **があります**。 |
| **Sid** | ローカル ユーザー Sid またはユーザー Sid グループ、または AD オブジェクトの Sid は、このポリシーを特定のユーザー またはユーザー グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの Sid を含め、Sid を使用しないエントリは、コンピューター上にポリシーを適用する方法を意味します。 |  |
| **ComputerSid** | ローカル コンピューター Sid またはコンピューター Sid グループ、または AD オブジェクトの Sid は、このポリシーを特定のコンピューターまたはコンピューター グループに適用するかどうかを定義します。1 つのエントリには最大 1 つの ComputerSid を指定し、ComputerSid を使用しないエントリはコンピューター上にポリシーを適用します。 特定のユーザーと特定のコンピューターにエントリを適用する場合は、Sid と ComputerSid の両方を同じエントリに追加します。 |  |
| **オプション** | 通知を表示するかどうかを定義します。 |**[許可の種類] が選択されている場合**: <p>0: 何も<p>4: この **エントリに対して AuditAllowed** と **AuditDenied を** 無効にします。 Allow が **発生** し、AuditAllowed が設定されている場合でも、システムはイベントを送信しない。 <p>8: ファイル情報をキャプチャし、書き込みアクセスの証拠としてファイルのコピーを持つ。 <p>16: 書き込みアクセスのファイル情報をキャプチャします。 <p>**[拒否] と入力すると、次の項目が選択されます**。 <p>0: 何も<p>4: この **エントリの AuditDenied** を無効にします。 ブロックが **発生** し、AuditDenied が構成されている場合でも、システムは通知を表示されません。 <p>**Type **AuditAllowed が** 選択されている場合**: <p>0: 何も <p>1: 何も <p>2: 送信イベント<p>3: イベントの送信 <p> **Type **AuditDenied が** 選択されている場合**: <p>0: 何も <p>1: 通知を表示する <p>2: 送信イベント<p>3: 通知を表示し、イベントを送信する |
|AccessMask|アクセスを定義します。 | **ディスク レベルのアクセス**: <p>1: 読み取り <p>2: 書き込み <p>4: 実行 <p>**ファイル システム レベルのアクセス**: <p>8: ファイル システムの読み取り <p>16: ファイル システム書き込み <p>32: ファイル システムの実行 <p><p>バイナリ OR 操作を実行すると、複数のアクセスを使用できます。たとえば、読み取りおよび書き込みおよび実行の AccessMask は 7 になります。読み取りおよび書き込み用の AccessMask は 3 です。|

## <a name="common-removable-storage-access-control-scenarios"></a>一般的なリムーバブル Storage Access Controlシナリオ

リムーバブル デバイスのMicrosoft Defender for Endpoint Storage Access Control、一般的なシナリオをまとめました。

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>シナリオ 1: すべてのユーザーへの書き込みおよび実行アクセスを防止するが、特定の承認済み USB を許可する

1. グループを作成する

    1. グループ 1: リムーバブル 記憶域と CD/DVD。 リムーバブル 記憶域と CD/DVD の例は、グループ **9b28fae8-72f7-4267-a1a5-685f747a7146** のサンプルの Any [Removable Storage および CD-DVD Group.xmlファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)です。

    2. グループ 2: デバイスのプロパティに基づく承認済み USB。 この使用例の例は、サンプルの承認済み [USB Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルのインスタンス ID - グループ **65fa649a-a111-4912-9294-fb6337a25038** です。

    > [!TIP]
    > 値 `&` で置 `&amp;` き換える。

2. ポリシーの作成

    1. ポリシー 1: 書き込みおよび実行アクセスをブロックしますが、承認済みの USB を許可します。 この使用例の例は、シナリオ 1 ブロック書き込みおよび実行アクセスのサンプルの PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** ですが、承認済みの [USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルを許可します。

    2. ポリシー 2: 許可された USB への書き込みおよび実行アクセスを監査します。 この使用例の例として、PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** (シナリオ [1 監査](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 書き込みおよび承認済み USBs.xmlファイルへのアクセスの実行) があります。

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>シナリオ 2: 特定の承認されていない USB をブロックするを含むすべてのユーザーへの書き込みおよび実行アクセスを監査する

1. グループを作成する

    1. グループ 1: リムーバブル 記憶域と CD/DVD。 この使用例の例は、サンプル Any [Removable Storage および CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルのグループ **9b28fae8-72f7-4267-a1a5-685f747a7146** です。

    2. グループ 2: サンプルの未承認の USB Group.xmlファイルのデバイス プロパティに基づく未承認 [の USB](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)(たとえば、Vendor ID/Product ID、Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038**)。

    > [!TIP]
    > 値 `&` で置 `&amp;` き換える。

2. ポリシーの作成

    1. ポリシー 1: 特定の承認されていない USB をブロックする権限を持つすべてのユーザーに対する書き込みおよび実行アクセスをブロックします。 この使用例の例として、PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** のサンプルシナリオ 2 Audit Write and Execute access to all but block specific 未承認 [の USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ファイルがあります。

    2. ポリシー 2: 他のユーザーへの書き込みおよび実行アクセスを監査します。 この使用例の例は、シナリオ [2 Audit Write and Execute](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) access to others.xmlファイルの PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** です。

## <a name="deploying-and-managing-policy-via-group-policy"></a>サーバー経由でのポリシーの展開と管理グループ ポリシー

リムーバブル Storage Access Control機能を使用すると、ユーザーまたはデバイスグループ ポリシー両方にポリシーを適用できます。

### <a name="licensing"></a>ライセンス

リムーバブル サーバーの使用を開始する前にStorage Access Controlサブスクリプションを確認[するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 リムーバブル ファイルにアクセスして使用するにはStorage Access Control、削除または削除Microsoft 365 E3必要Microsoft 365 E5。

### <a name="deploying-policy-via-group-policy"></a>ポリシーの展開は、グループ ポリシー

1. すべてのグループを 1 つの `<Groups>` `</Groups>` xml ファイルに結合します。

    次の図は、シナリオ 1: すべてへの書き込みおよび実行アクセスを防止するが、特定の承認済み [USB を許可する例を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイスで特定の承認済み USB を許可する構成設定" lightbox="images/prevent-write-access-allow-usb.png":::

2. すべてのルールを 1 つの `<PolicyRules>` `</PolicyRules>` xml ファイルに結合します。

    特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。 ポリシー Entry に SID がない場合、エントリはコンピューターのすべてのログイン インスタンスに適用されます。
    
    書き込みアクセスのファイル情報を監視する場合は、右のオプション (16) で右の AccessMask を使用します。ファイル情報のキャプチャの [例を次に示します](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Audit%20File%20Information.xml)。

    次の図は、SID プロパティの使用法とシナリオ 1: 書き込みおよび実行アクセスを許可するが、特定の承認済み USB を許可するシナリオ 1 の例 [を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用法を示すコード" lightbox="images/usage-sid-property.png":::

3. ルールとグループ XML ファイルの両方をネットワーク共有フォルダーに保存し、ネットワーク共有フォルダー のパスを グループ ポリシー の設定に入 **れる:** \>  \> コンピューター構成管理用テンプレート **Windows コンポーネント** \> **Microsoft Defender ウイルス対策** \> Device **Control**: 'デバイス制御ポリシー グループの定義 **'** と **'デバイス制御ポリシー ルールの定義' をクリックします**。

   グループ ポリシー でポリシー構成 UX が見つからない場合は、[Raw] を選択してから [名前を付けて保存] を選択して [、WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルをダウンロード **できます**。

   - ポリシーを持つには、ターゲット コンピューターがネットワーク共有にアクセスできる必要があります。 ただし、ポリシーを読み取った後は、コンピューターの再起動後も、ネットワーク共有接続は不要になります。

    :::image type="content" source="images/device-control.png" alt-text="[デバイス制御] 画面" lightbox="images/device-control.png":::

4. 既定の適用: ポリシーがない場合は、既定のアクセス (拒否または許可) をリムーバブル メディアに設定できます。 たとえば、RemovableMediaDevices のポリシー (Deny または Allow) しか持っていませんが、CdRomDevices または WpdDevices のポリシーを持たなかったり、このポリシーを使用して既定の拒否を設定すると、CdRomDevices または WpdDevices への読み取り/書き込み/実行アクセスがブロックされます。

   - この設定を展開すると、[既定の許可] または [ **既定の拒否]** **が表示されます**。
   - この設定を構成するときに、ディスク レベルとファイル システム レベルの両方の AccessMask を検討します。たとえば、Default Deny を使用するが、特定の記憶域を許可する場合は、ディスク レベルとファイル システム レベルの両方のアクセスを許可する必要がある場合は、AccessMask を 63 に設定する必要があります。

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="既定の許可または既定の拒否 PowerShell コード":::

5. [リムーバブル デバイスの有効化Storage Access Control無効にする]: この値を設定して、リムーバブル ファイルを一時的に無効Storage Access Control。

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="デバイスコントロールの設定":::

   - この設定を展開すると、[有効] または [無効 **] が** 表示 **されます**。 無効とは、このコンピューターがリムーバブル ポリシーを実行Storage Access Control意味します。

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="PowerShell コードでデバイスコントロールを有効または無効にする":::

6. ファイルのコピーの場所を設定する: 書き込みアクセスが発生した場合にファイルのコピーを作成する場合は、システムがコピーを保存できる場所を設定する必要があります。
    
    これを右の AccessMask と Option と共に展開します。上記の手順 2 を参照してください。

    :::image type="content" source="../../media/define-device-control-policy-rules.png" alt-text="グループ ポリシー - ファイル証拠の locaiton を設定する":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>OMA-URI を使用してポリシー Intune展開および管理する

リムーバブル Storage Access Control機能を使用すると、OMA-URI 経由でユーザーまたはデバイス、または両方にポリシーを適用できます。

### <a name="licensing-requirements"></a>ライセンスの要件

リムーバブル サーバーの使用を開始する前にStorage Access Controlサブスクリプションを確認[するMicrosoft 365があります](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)。 リムーバブル ファイルにアクセスして使用するにはStorage Access Control、削除または削除Microsoft 365 E3必要Microsoft 365 E5。

### <a name="permission"></a>アクセス許可

ポリシーを展開する場合Intuneアカウントには、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可が必要です。 カスタム ロールを作成するか、これらのアクセス許可を持つ組み込みロールを使用できます。

- ポリシーとプロファイル マネージャーの役割

- デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示権限を有効にしたカスタム ロール

- 全体管理者

### <a name="deploying-policy-via-oma-uri"></a>OMA-URI によるポリシーの展開

Microsoft エンドポイント マネージャー センター (<https://endpoint.microsoft.com/>) \> **デバイス** \> **構成**\>プロファイル プロファイル **の**\>作成プロファイル プラットフォーム: Windows 10以降 **&プロファイル: カスタム**

1. グループごとに、OMA-URI ルールを作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      たとえば、サンプル **内のリムーバブル 記憶域と CD/DVD** グループの場合、リンクは次のようになります。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - データ型: 文字列 (XML ファイル)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="[行の追加] ページの [データ型] フィールド" lightbox="images/xml-data-type-string.png":::

2. ポリシーごとに、OMA-URI も作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      たとえば、ブロック書き込みおよび実行アクセスの場合、サンプルで承認 **された USB** ルールを許可するには、次のリンクが必要です。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - データ型: 文字列 (XML ファイル)
       
    書き込みアクセスのファイル情報を監視する場合は、右のオプション (16) で右の AccessMask を使用します。ファイル情報のキャプチャの [例を次に示します](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20File%20Information.xml)。

3. 既定の適用: ポリシーがない場合は、既定のアクセス (拒否または許可) をリムーバブル メディアに設定できます。 たとえば、RemovableMediaDevices のポリシー (Deny または Allow) しか持っていませんが、CdRomDevices または WpdDevices のポリシーを持たなかったり、このポリシーを使用して既定の拒否を設定すると、CdRomDevices または WpdDevices への読み取り/書き込み/実行アクセスがブロックされます。

    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - データ型: Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - この設定を展開すると、[既定の許可] または **[既定の拒否]** **が表示されます。**
    - この設定を構成するときに、ディスク レベルとファイル システム レベルの両方の AccessMask を検討します。たとえば、Default Deny を使用するが、特定の記憶域を許可する場合は、ディスク レベルとファイル システム レベルの両方のアクセスを許可する必要がある場合は、AccessMask を 63 に設定する必要があります。

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="既定の強制 PowerShell コードを許可する":::

4. [リムーバブル デバイスの有効化Storage Access Control無効にする]: この値を設定して、リムーバブル ファイルを一時的に無効Storage Access Control。

   - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - データ型: Int `Disable: 0`
     `Enable: 1`

   - この設定を展開すると、[有効] または [無効 **] が** 表示 **されます。**

    **無効** にすると、このコンピューターでリムーバブル ポリシーが実行Storage Access Controlされません。

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="PowerShell コードStorage Access Control削除可能なファイル":::

5. ファイルのコピーの場所を設定します。書き込みアクセスが発生した場合にファイルのコピーを作成する場合は、システムがコピーを保存できる場所を設定する必要があります。
    
    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation;**username**;**password**`

    - データ型 : String
    
    これを右の AccessMask と右のオプションと共に展開する必要があります。上記の手順 2 を参照してください。

    :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="ファイル証拠に locaiton を設定する":::
    
## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>ユーザー インターフェイスを使用してポリシーを展開Intune管理する

(*近日公開予定!* この機能は、管理センター () のMicrosoft エンドポイント マネージャー使用できます<https://endpoint.microsoft.com/>。 [Endpoint **SecurityAttack Surface** >  **ReductionCreate** >  **Policy] に移動します**。 [**プラットフォーム: Windows 10プロファイル:** デバイス **コントロール] を選択します**。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>デバイス コントロールのリムーバブル データStorage Access Controlを表示Microsoft Defender for Endpoint

[[Microsoft 365 Defender] ポータルには、](https://security.microsoft.com/advanced-hunting)Device Control リムーバブル サーバーによってトリガーされたイベントがStorage Access Control。 セキュリティにアクセスするにはMicrosoft 365サブスクリプションが必要です。

- Microsoft 365 E5 レポートの詳細

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
    
:::image type="content" source="images/block-removable-storage.png" alt-text="リムーバブル 記憶域のブロックを示す画面。":::


## <a name="frequently-asked-questions"></a>よく寄せられる質問


### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>グループ ID/PolicyRule ID/Entry ID の GUID を生成する方法

オンライン または PowerShell を使用オープンソース GUID を生成する方法 - PowerShell を使用して [GUID を生成する方法](/powershell/module/microsoft.powershell.utility/new-guid?msclkid=c1398a25a6d911ec9c888875fa1f24f5&view=powershell-7.2)
    
![image](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)
    
### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>USB の最大数に対するリムーバブル 記憶域メディアの制限は何ですか?

100,000 メディアを持つ 1 つの USB グループ (最大 7 MB のサイズ) を検証しました。 このポリシーは、パフォーマンスの問題Intune GPO の両方で動作します。

### <a name="why-does-the-policy-not-work"></a>ポリシーが機能しない理由

1. 最も一般的な理由は、必要なマルウェア対策 [クライアントのバージョンがない点です](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)。

2. もう 1 つの理由は、XML ファイルが正しく書式設定されていない、たとえば、XML ファイル内の "&" 文字に対して正しいマークダウン書式を使用していない、またはテキスト エディターがファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBF を追加し、XML 解析が機能しないことです。 1 つの簡単な解決策は、サンプル ファイルを [ダウンロード](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) して ( **[Raw** ] を選択 **し、[名前** を付けて保存] を選択) してから更新することです。

3. グループ ポリシー 経由でポリシーを展開および管理する場合は、すべての PolicyRule を PolicyRules と呼ばれる親ノード内の 1 つの XML ファイルに結合し、すべてのグループを Groups という親ノード内の 1 つの XML ファイルに結合してください。Intune を管理する場合は、PolicyRule 1 つの XML ファイル 、同じもの、1 つのグループ 1 XML ファイルを保持してください。
    
それでも動作しない場合は、管理者と cmd を実行してサポート キャブに連絡し、サポート キャブを共有することができます。"%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>[デバイス制御ポリシー グループの定義] と [デバイス制御ポリシー ルールの定義] の構成 UX は、自分のサーバーにグループ ポリシー

グループ ポリシー 構成 UX はバックポートしないが、[WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルで [Raw] と [名前を付けて保存] をクリックすると、関連する adml ファイルと admx ファイルを取得できます。

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>最新のポリシーがターゲット コンピューターに展開されているかどうかを確認する方法

管理者として PowerShell で 'Get-MpComputerStatus' を実行できます。 次の値は、ターゲット コンピューターに最新のポリシーが適用されているかどうかを示します。

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>組織で最新のマルウェア対策クライアント バージョンを使用しているコンピューターを確認する方法

次のクエリを使用して、セキュリティ ポータルでマルウェア対策クライアントMicrosoft 365取得できます。

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
