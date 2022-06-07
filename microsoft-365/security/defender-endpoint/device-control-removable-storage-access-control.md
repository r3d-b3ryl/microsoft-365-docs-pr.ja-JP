---
title: Microsoft Defender for Endpoint Device Control リムーバブル ストレージ アクセス制御、リムーバブル ストレージ メディア
description: Microsoft Defender for Endpoint に関するウォークスルー
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
ms.date: 06/06/2022
ms.openlocfilehash: 68beef5a01206ef08a87f74d53767fdd74d37a14
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65923502"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender for Endpoint Device Control リムーバブル ストレージ アクセス制御

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> この製品のグループ ポリシー管理と Intune OMA-URI/カスタム ポリシー管理が一般公開されました (4.18.2106): [「Tech Community ブログ: Microsoft Defender for Endpoint でリムーバブル ストレージとプリンターを保護](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806)する」を参照してください。

Microsoft Defender for Endpoint Device Control リムーバブル ストレージ アクセス制御を使用すると、次のタスクを実行できます。

- 除外の有無にかかわらず、リムーバブル ストレージへの読み取り、書き込み、または実行アクセスの監査、許可、防止

|特権|アクセス許可|
|---|---|
|Access|読み取り、書き込み、実行|
|アクション モード|監査、許可、禁止|
|CSP サポート|はい|
|GPO のサポート|はい|
|ユーザー ベースのサポート|はい|
|マシンベースのサポート|はい|

|機能|説明|Intune を使用してデプロイする|グループ ポリシーを使用して展開する|
|---|---|---|---|
|リムーバブル メディア グループの作成|再利用可能なリムーバブル メディア グループを作成できます|セクション「[OMA-URI を使用したポリシーの展開](#deploying-policy-via-oma-uri)」の手順 1 | 「[グループ ポリシーを使用したポリシーの展開](#deploying-policy-via-group-policy)」セクションの手順 1|
|ポリシーの作成|各リムーバブル メディア グループを適用するポリシーを作成できます|セクション「[OMA-URI を使用したポリシーの展開](#deploying-policy-via-oma-uri)」セクションの手順 2 | [「グループ ポリシーを使用したポリシーの展開](#deploying-policy-via-group-policy)」セクションの手順 2 と 3 |
|既定の適用|ポリシーがない場合は、リムーバブル メディアに既定のアクセス (拒否または許可) を設定できます|セクション「[OMA-URI を使用したポリシーの展開](#deploying-policy-via-oma-uri)」セクションの手順 3 | 「[グループ ポリシーを使用したポリシーの展開](#deploying-policy-via-group-policy)」セクションの手順 4 |
|リムーバブル ストレージ アクセス制御を有効または無効にする|[無効] を設定すると、このマシンのリムーバブル ストレージ アクセス制御ポリシーが無効になります| セクション「[OMA-URI を使用したポリシーの展開](#deploying-policy-via-oma-uri)」セクションの手順 4 | 「[グループ ポリシーを使用したポリシーの展開](#deploying-policy-via-group-policy)」セクションの手順 5 |
|ファイル情報をキャプチャする|書き込みアクセスが発生したときにファイル情報をキャプチャするポリシーを作成できます| セクション「[OMA-URI を使用したポリシーの展開](#deploying-policy-via-oma-uri)」セクションの手順 2 と 5 | 「[グループ ポリシーを使用したポリシーの展開](#deploying-policy-via-group-policy)」セクションの手順 2 と 6 |

## <a name="prepare-your-endpoints"></a>エンドポイントを準備する

マルウェア対策クライアント バージョン **4.18.2103.3 以降の Windows 10 および Windows 11** デバイスにリムーバブル ストレージ アクセス制御を展開します。

- **4.18.2104 以降**: SerialNumberId、VID_PID、filepath ベースの GPO サポート、ComputerSid の追加

- **4.18.2105 以降**: HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId のワイルドカード サポートを追加します。特定のマシン上の特定のユーザーの組み合わせ、リムーバブル SSD (SanDisk Extreme SSD)/USB Attached SCSI (UAS) のサポート

- **4.18.2107 以降**: Windows ポータブル デバイス (WPD) のサポート (タブレットなどのモバイル デバイスの場合) を追加します。[高度なハンティング](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)に AccountName を追加する

:::image type="content" source="images/powershell.png" alt-text="PowerShell インターフェイス" lightbox="images/powershell.png":::

> [!NOTE]
> Windows セキュリティの状態に関係なくリムーバブル ストレージ アクセス制御を実行できるため、Windows セキュリティ コンポーネントをアクティブにする必要はありません。

## <a name="policy-properties"></a>ポリシーのプロパティ

次のプロパティを使用して、リムーバブル ストレージ グループを作成できます。

> [!NOTE]
> XML コメント表記 `<!-- COMMENT -->` を使用するコメントは、ルールおよびグループ XML ファイルで使用できますが、XML ファイルの最初の行ではなく、最初の XML タグ内にある必要があります。

### <a name="removable-storage-group"></a>リムーバブル ストレージ グループ

|プロパティ名|説明|オプション|
|---|---|---|
|**グループ ID**|GUID (一意の ID) はグループを表し、ポリシーで GroupId として使用されます。||
|**DescriptorIdList**|グループ内でカバーするために使用するデバイス プロパティを一覧表示します。 各デバイス プロパティの詳細については、 [デバイスのプロパティ](device-control-removable-storage-protection.md) に関するページを参照してください。 すべてのプロパティで大文字と小文字が区別されます。 |**PrimaryId**: `RemovableMediaDevices`, , `CdRomDevices``WpdDevices`<p>**BusId**: たとえば、USB、SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**: InstancePathId は、たとえば、システム `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`内のデバイスを一意に識別する文字列です。 末尾の数値 (&0 など) は使用可能なスロットを表し、デバイスからデバイスに変更される場合があります。 最適な結果を得るには、最後にワイルドカードを使用します。 たとえば、「 `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*` 」のように入力します。<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: この正確な VID/PID ペアと一致する<p>`_55E0`: PID=55E0 の任意のメディアと一致する <p>`0751_`: VID=0751 で任意のメディアと一致する|
|**MatchType**|複数のデバイス プロパティが使用されている場合は、 `DescriptorIDList`MatchType によってリレーションシップが定義されます。|**MatchAll**: 次の属性`DescriptorIdList`は **And** リレーションシップになります。たとえば、管理者が接続されているすべての USB に対して`InstancePathID`、USB `DeviceID` が両方の値を満たしているかどうかを確認します。 <p> **MatchAny**: DescriptorIdList の下の属性は **Or** リレーションシップになります。たとえば、管理者 `DeviceID` が接続されているすべての USB に対して `InstancePathID`、USB が同じ **DeviceID** または **InstanceID** 値を持っている限り、システムは適用を行います。 |

### <a name="access-control-policy"></a>アクセス制御ポリシー

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

## <a name="common-removable-storage-access-control-scenarios"></a>リムーバブル ストレージ アクセス制御の一般的なシナリオ

Microsoft Defender for Endpoint リムーバブル ストレージ アクセス制御について理解を深めるために、一般的なシナリオをいくつかまとめ、フォローしています。

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

    2. グループ 2: デバイスのプロパティに基づく未承認の USB(ベンダー ID/製品 ID、フレンドリ名- グループ **65fa649a-a111-4912-9294-fb6337a2503** [Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 8 など)

    > [!TIP]
    > 値に置`&amp;`き換えます`&`。

2. ポリシーの作成

    1. ポリシー 1: 特定の未承認の USB をブロックする以外のすべての書き込みと実行アクセスをブロックします。 このユース ケースの例は、サンプル シナリオ 2 の PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** です。ただし、 [特定の未承認のUSBs.xmlファイルへのアクセスをブロック](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) します。

    2. ポリシー 2: 他のユーザーへの書き込みと実行アクセスを監査します。 このユース ケースの例として、サンプル シナリオ 2 のサンプル シナリオ 2 の PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** が [others.xmlファイルへのアクセスを監査することです](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) 。

## <a name="deploying-and-managing-policy-via-group-policy"></a>グループ ポリシーを使用したポリシーの展開と管理

リムーバブル ストレージ アクセス制御機能を使用すると、グループ ポリシーを使用してポリシーをユーザーまたはデバイス、またはその両方に適用できます。

### <a name="licensing"></a>ライセンス

リムーバブル ストレージ アクセス制御を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)を確認する必要があります。 リムーバブル ストレージ アクセス制御にアクセスして使用するには、Microsoft 365 E3 または Microsoft 365 E5 が必要です。

### <a name="deploying-policy-via-group-policy"></a>グループ ポリシーを使用したポリシーの展開

1. 内`<Groups>``</Groups>`のすべてのグループを 1 つの xml ファイルに結合します。

    次の図は [、シナリオ 1: 特定の承認済み USB を許可する以外のすべてのユーザーへの書き込みと実行のアクセスを禁止する例を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="デバイスで特定の承認済み USB を許可する構成設定" lightbox="images/prevent-write-access-allow-usb.png":::

2. すべてのルールを `<PolicyRules>` `</PolicyRules>` 1 つの xml ファイルに結合します。

    特定のユーザーを制限する場合は、エントリに SID プロパティを使用します。 ポリシーエントリに SID がない場合、エントリはマシンのすべてのログイン インスタンスに適用されます。

    書き込みアクセスのファイル情報を監視する場合は、適切なオプション (16) で適切な AccessMask を使用します。 [キャプチャ ファイル情報](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Audit%20File%20Information.xml)の例を次に示します。

    次の図は、SID プロパティの使用方法と、「 [シナリオ 1: 特定の承認済み USB を許可する以外のすべてのユーザーへの書き込みと実行のアクセスを禁止する」の例を示しています](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)。

    :::image type="content" source="images/usage-sid-property.png" alt-text="SID プロパティ属性の使用方法を示すコード" lightbox="images/usage-sid-property.png":::

3. ネットワーク共有フォルダーにルールファイルとグループ XML ファイルの両方を保存し、ネットワーク共有フォルダーのパスをグループ ポリシー設定に配置します。 **[コンピューター構成** \> **管理用テンプレート** \> **] Windows コンポーネント** \> **の Microsoft Defender ウイルス対策** \> **デバイス制御**: **"デバイス制御ポリシー グループの定義"** と **"デバイス制御ポリシー規則の定義"** を選択します。

   グループ ポリシーでポリシー構成 UX が見つからない場合は、[**未加工**] を選択してから **[名前を付けて保存]** を選択して、[WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルをダウンロードできます。

   - ターゲット マシンは、ポリシーを持つネットワーク共有にアクセスできる必要があります。 ただし、ポリシーを読み取ると、マシンの再起動後でも、ネットワーク共有接続は不要になります。

    :::image type="content" source="images/device-control.png" alt-text="[デバイス制御] 画面" lightbox="images/device-control.png":::

4. 既定の適用: ポリシーがない場合は、既定のアクセス (拒否または許可) をリムーバブル メディアに設定できます。 たとえば、RemovableMediaDevices のポリシー (拒否または許可) しか持っていないが、CdRomDevices または WpdDevices のポリシーはなく、このポリシーを使用して既定の拒否を設定すると、CdRomDevices または WpdDevices への読み取り/書き込み/実行アクセスがブロックされます。

   - この設定を展開すると、 **既定の許可** または **既定の拒否** が表示されます。
   - この設定を構成するときは、ディスク レベルとファイル システム レベルの AccessMask の両方を考慮してください。たとえば、既定で拒否するが特定のストレージを許可する場合は、ディスク レベルとファイル システム レベルの両方のアクセスを許可する必要がある場合は、AccessMask を 63 に設定する必要があります。

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="既定の許可または既定の拒否 PowerShell コード":::

5. リムーバブル ストレージ アクセス制御を有効または無効にする: この値を設定して、リムーバブル ストレージ アクセス制御を一時的に無効にすることができます。

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="デバイスコントロールの設定":::

   - この設定を展開すると、[ **有効]** または **[無効]** と表示されます。 [無効] は、このマシンにリムーバブル ストレージ アクセス制御ポリシーが実行されないことを意味します。

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="PowerShell コードでデバイスコントロールを有効または無効にする":::

6. ファイルのコピーの場所を設定する:書き込みアクセスが行われるときにファイルのコピーを作成する場合は、システムがコピーを保存できる場所を設定する必要があります。

    これを適切な AccessMask と Option と共にデプロイします。上記の手順 2 を参照してください。

    :::image type="content" source="../../media/define-device-control-policy-rules.png" alt-text="グループ ポリシー - ファイル証拠の locaiton を設定する":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Intune OMA-URI を使用したポリシーの展開と管理

リムーバブル ストレージ アクセス制御機能を使用すると、OMA-URI を使用してポリシーをユーザーまたはデバイス、またはその両方に適用できます。

### <a name="licensing-requirements"></a>ライセンスの要件

リムーバブル ストレージ アクセス制御を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)を確認する必要があります。 リムーバブル ストレージ アクセス制御にアクセスして使用するには、Microsoft 365 E3 または Microsoft 365 E5 が必要です。

### <a name="permission"></a>アクセス許可

Intune でのポリシーの展開では、デバイス構成プロファイルを作成、編集、更新、または削除するためのアクセス許可がアカウントに付与されている必要があります。 カスタム ロールを作成することも、これらのアクセス許可を持つ組み込みロールを使用することもできます。

- ポリシーとプロファイル マネージャーのロール

- デバイス構成プロファイルに対してレポートの作成/編集/更新/読み取り/削除/表示のアクセス許可が有効になっているカスタム ロール

- グローバル管理者

### <a name="deploying-policy-via-oma-uri"></a>OMA-URI を使用したポリシーのデプロイ

Microsoft Endpoint Manager 管理センター (<https://endpoint.microsoft.com/>) \> **デバイス** \> **構成プロファイル** \> **プロファイル作成プロファイル** \> **プラットフォーム: Windows 10 以降の& プロファイル: カスタム**

1. グループごとに、OMA-URI 規則を作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      たとえば、サンプル内 **のリムーバブル ストレージと CD/DVD** グループの場合、リンクは次のようになります。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - データ型: 文字列 (XML ファイル)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="[行の追加] ページの [データ型] フィールド" lightbox="images/xml-data-type-string.png":::

2. ポリシーごとに、OMA-URI も作成します。

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      たとえば、サンプルの **書き込みと実行アクセスをブロックし、承認された USB** ルールを許可する場合、リンクは次のようになります。

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - データ型: 文字列 (XML ファイル)

    書き込みアクセスのファイル情報を監視する場合は、適切なオプション (16) で適切な AccessMask を使用します。 [キャプチャ ファイル情報](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20File%20Information.xml)の例を次に示します。

3. 既定の適用: ポリシーがない場合は、既定のアクセス (拒否または許可) をリムーバブル メディアに設定できます。 たとえば、RemovableMediaDevices のポリシー (拒否または許可) しか持っていないが、CdRomDevices または WpdDevices のポリシーはなく、このポリシーを使用して既定の拒否を設定すると、CdRomDevices または WpdDevices への読み取り/書き込み/実行アクセスがブロックされます。

    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - データ型: Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - この設定を展開すると、**既定の許可** または **既定の拒否** が表示されます
    - この設定を構成するときは、ディスク レベルとファイル システム レベルの AccessMask の両方を考慮してください。たとえば、既定で拒否するが特定のストレージを許可する場合は、ディスク レベルとファイル システム レベルの両方のアクセスを許可する必要がある場合は、AccessMask を 63 に設定する必要があります。

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="既定の適用で PowerShell コードを許可する":::

4. リムーバブル ストレージ アクセス制御を有効または無効にする: この値を設定して、リムーバブル ストレージ アクセス制御を一時的に無効にすることができます。

   - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - データ型: Int `Disable: 0`
     `Enable: 1`

   - この設定を展開すると、[ **有効]** または **[無効] と表示されます。**

    **[無効]** は、このマシンにリムーバブル ストレージ アクセス制御ポリシーが実行されていないという意味です。

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="PowerShell コードのリムーバブル ストレージ アクセス制御":::

5. ファイルのコピーの場所を設定します。書き込みアクセスが行われるときにファイルのコピーを作成する場合は、システムがコピーを保存できる場所を設定する必要があります。

    - OMA-URI: './Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation

    - データ型 : String

    これを適切な AccessMask と適切なオプションと共にデプロイする必要があります。上記の手順 2 を参照してください。

    :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="ファイル証拠の locaiton を設定する":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Intune ユーザー インターフェイスを使用したポリシーの展開と管理

(*近日公開予定)* この機能は、Microsoft Endpoint Manager 管理センター (<https://endpoint.microsoft.com/>) で使用できます。 **Endpoint Security Attack** > **Surface Reduction** > **Create Policy** に移動します。 [ **プラットフォーム: Windows 10 以降** ] と [ **プロファイル: デバイス制御**] を選択します。

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でデバイス コントロールのリムーバブル ストレージ アクセス制御データを表示する

[Microsoft 365 Defender ポータル](https://security.microsoft.com/advanced-hunting)には、デバイスコントロールリムーバブル ストレージ アクセス制御によってトリガーされるイベントが表示されます。 Microsoft 365 セキュリティにアクセスするには、次のサブスクリプションが必要です。

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

オンライン オープン ソースまたは PowerShell を使用して GUID を生成できます 。 [PowerShell を使用して GUID を生成する方法](/powershell/module/microsoft.powershell.utility/new-guid)

![image](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

### <a name="what-are-the-removable-storage-media-and-policy-limitations"></a>リムーバブル ストレージ メディアとポリシーの制限事項は何ですか?

Microsoft Endpoint Manager 管理センター (Intune) から、または Microsoft Graph API を使用してバックエンド呼び出しが行われるため、バックエンド呼び出しは OMA-URI (読み取りまたは更新する PATCH) を介して行われるため、制限は、XML ファイル用に正式に 350,000 文字である Microsoft の任意の OMA-URI カスタム構成プロファイルと同じです。 
    
たとえば、特定のユーザーを "許可"/"監査許可" するためにユーザー SID ごとに 2 つのエントリ ブロックが必要で、最後に "Deny" all に 2 つのエントリ ブロックが必要な場合は、2,276 人のユーザーを管理できます。 

### <a name="why-does-the-policy-not-work"></a>ポリシーが機能しないのはなぜですか?

1. 最も一般的な理由は、必要な [マルウェア対策クライアント バージョン](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)がないことです。

2. もう 1 つの理由は、XML ファイルが正しく書式設定されていない、たとえば、XML ファイル内の "&" 文字に正しいマークダウン書式を使用していない場合や、テキスト エディターでファイルの先頭にバイト オーダー マーク (BOM) 0xEF 0xBB 0xBFが追加され、XML 解析が機能しないことです。 簡単な解決策の 1 つは、 [サンプル ファイル](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) をダウンロードして ( **[未加工** ] を選択してから **[名前を付けて保存]** を選択して) 更新することです。

3. グループ ポリシーを使用してポリシーを展開および管理する場合は、PolicyRule を PolicyRules という親ノード内の 1 つの XML ファイルに結合し、すべてのグループをグループという親ノード内の 1 つの XML ファイルに結合してください。Intune を使用して管理する場合は、1 つの PolicyRule 1 つの XML ファイル (同じこと)、1 つのグループ 1 つの XML ファイルを保持します。

それでも動作しない場合は、管理者と cmd を実行してサポート cab を共有してください。 "%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>グループ ポリシーに "デバイス制御ポリシー グループの定義" と "デバイス制御ポリシー ルールの定義" の構成 UX がありません

グループ ポリシー構成 UX はバックポートしませんが、 [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) ファイルと [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) ファイルで [未加工] と [名前を付けて保存] をクリックすると、関連する adml ファイルと admx ファイルを引き続き取得できます。

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
