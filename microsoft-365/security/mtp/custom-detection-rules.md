---
title: Microsoft の脅威保護でカスタムの検出ルールを作成および管理する
description: 高度な検索クエリに基づいてカスタムの検出ルールを作成および管理する方法について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、ユーザー設定の検出、ルール、スキーマ、kusto、microsoft 365、Microsoft Threat Protection、RBAC、アクセス許可、Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a84c568d1411cf21c23e59cabad955c40c18ac6
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498365"
---
# <a name="create-and-manage-custom-detections-rules"></a>カスタムの検出ルールを作成および管理する

**適用対象:**
- Microsoft Threat Protection

[高度な](advanced-hunting-overview.md)検索クエリから構築されたカスタム検出ルールを使用すると、疑いのある違反のアクティビティや不適切なエンドポイントを含む、さまざまなイベントやシステム状態を事前に監視できます。 それらを定期的に実行するように設定して、一致するものがある場合は警告を生成し、応答アクションを実行することができます。

## <a name="required-permissions-for-managing-custom-detections"></a>ユーザー設定の検出を管理するために必要なアクセス許可

ユーザー設定の検出を管理するには、次のいずれかの役割を割り当てる必要があります。

- **セキュリティ管理者**: セキュリティ管理者またはセキュリティ管理者の役割は、Microsoft 365 セキュリティセンターとさまざまなポータルおよびサービスのさまざまなセキュリティ設定を管理するための[Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)です。

- **セキュリティオペレーター** —セキュリティオペレーターの役割は、通知を管理するための[Azure Active Directory の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator)で、Microsoft 365 セキュリティセンターのすべての情報を含む、セキュリティ関連の機能に対するグローバルな読み取り専用アクセス権を持ちます。 この役割は、Microsoft Defender ATP で役割ベースのアクセス制御 (RBAC) がオフになっている場合にのみ、カスタムの検出を管理するのに十分です。 RBAC を構成している場合は、Microsoft Defender ATP の [**セキュリティ設定の管理**] アクセス許可も必要です。

必要なアクセス許可を管理するために、**全体管理者**は次の操作を行うことができます。

- 「 **Roles**security admin」の下にある[Microsoft 365 管理センター](https://admin.microsoft.com/)で、**セキュリティ管理者**または**セキュリティオペレーター**の役割を割り当て  >  **Security admin**ます。
- [アクセス許可の役割の**設定**] の下の microsoft defender の[セキュリティセンター](https://securitycenter.windows.com/)で、microsoft defender ATP の RBAC 設定を確認  >  **Permissions**  >  **Roles**します。 対応する役割を選択して、[**セキュリティ設定の管理**] アクセス許可を割り当てます。

> [!NOTE]
> ユーザー設定の検出を管理するために、**セキュリティオペレーター**は、RBAC が有効になっている場合、MICROSOFT Defender ATP の**セキュリティ設定の管理**権限を必要とします。

## <a name="create-a-custom-detection-rule"></a>カスタム検出ルールを作成する
### <a name="1-prepare-the-query"></a>1. クエリを準備します。

Microsoft 365 セキュリティセンターで、 **[高度な**検索] に移動して既存のクエリを選択するか、新しいクエリを作成します。 新しいクエリを使用する場合は、クエリを実行してエラーを特定し、考えられる結果を理解します。

#### <a name="required-columns-in-the-query-results"></a>クエリ結果に必要な列
カスタム検出ルールを作成するには、クエリは次の列を返す必要があります。

- `Timestamp`
- 次のいずれかのデバイス、ユーザー、またはメールボックスの列。
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(エンベロープ送信者またはリターンパスアドレス)
    - `SenderMailFromAddress`(電子メールクライアントによって表示される sender アドレス)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>[高度な検索スキーマ](advanced-hunting-schema-tables.md)に新しいテーブルが追加されると、追加のエンティティのサポートが追加されます。

検索結果をカスタマイズまたは集計するために or 演算子を使用しないような単純なクエリでは、 `project` `summarize` 通常、これらの共通の列が返されます。

より複雑なクエリでこれらの列が返されるようにするには、さまざまな方法があります。 たとえば、などの列の下にあるエンティティで集計およびカウントを行う場合は、 `DeviceId` `Timestamp` それぞれの一意に関係する最新のイベントから取得することによって返すことができ `DeviceId` ます。

以下のサンプルクエリは、ウイルス検出を使用して一意のデバイス () の数をカウント `DeviceId` し、この数を使用して、検出されたデバイスのみを検出します。 最新のを返すには `Timestamp` 、 `summarize` 演算子を関数で使用し `arg_max` ます。

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 新しいルールを作成し、通知の詳細を提供します。

クエリエディターでクエリを実行して、[**検出ルールの作成**] を選択し、次の通知の詳細を指定します。

- **検出名**—検出ルールの名前
- **頻度**—クエリを実行してアクションを実行する間隔。 [以下の追加のガイダンスを参照してください。](#rule-frequency)
- **アラートタイトル**-ルールによってトリガーされたアラートと共に表示されるタイトル
- **重要度**—ルールによって識別されるコンポーネントまたはアクティビティの潜在的なリスク
- **カテゴリ**—ルールによって識別される脅威コンポーネントまたはアクティビティ
- **MITRE att&** の「」: [MITRE ATT&](https://attack.mitre.org/)の「」フレームワークに記載されているように、ルールによって識別される1つまたは複数の攻撃手法。 このセクションは適用されず、マルウェア、ランサムウェア、不審なアクティビティ、不要なソフトウェアなど、特定の通知カテゴリに対して非表示になります。
- **Description** —ルールによって識別されたコンポーネントまたはアクティビティに関する詳細情報 
- **推奨**されるアクション-通知に応答する可能性があるその他のアクション。

#### <a name="rule-frequency"></a>ルールの頻度
保存すると、新しいまたは編集されたカスタム検出ルールが直ちに実行され、過去30日間のデータが一致するかどうかがチェックされます。 その後、ルールは固定された間隔で再び実行され、選択した頻度に基づいて、継続時間を確認します。

- **24 時間ごと**: 過去30日間のデータをチェックして、24時間ごとに実行します。
- **12 時間ごと**-過去24時間以内にデータをチェックして、12時間ごとに実行します。
- **3 時間ごと**—過去6時間にデータをチェックして、3時間ごとに実行します。
- 毎時に**1 時間ごと**に実行され、過去2時間のデータをチェックします。

検出を監視する頻度と一致する頻度を選択し、通知に応答するために組織の能力を考慮します。

### <a name="3-choose-the-impacted-entities"></a>3. 影響を受けるエンティティを選択します。
影響を受ける主なエンティティまたは影響を受けるエンティティがあることが予想されるクエリ結果内の列を特定します。 たとえば、クエリは送信者 ( `SenderFromAddress` または `SenderMailFromAddress` ) と受信者 () のアドレスを返す場合があり `RecipientEmailAddress` ます。 これらの列のうち、主な影響を受けるエンティティを識別することにより、サービスは関連するアラートの集約、インシデントの関連付け、およびターゲットの応答アクションの実行に役立てることができます。

エンティティの種類 (メールボックス、ユーザー、またはデバイス) ごとに1つの列のみを選択できます。 クエリで返されない列は選択できません。

### <a name="4-specify-actions"></a>4. アクションを指定します。
カスタム検出ルールは、クエリによって返されるデバイス、ファイル、またはユーザーに対して、自動的にアクションを実行できます。

#### <a name="actions-on-devices"></a>デバイスに対するアクション
これらのアクションは `DeviceId` 、クエリ結果の列にあるデバイスに適用されます。
- **分離デバイス**— MICROSOFT Defender ATP を使用して完全なネットワークの分離を適用し、デバイスがアプリケーションやサービスに接続できないようにします。 [Microsoft Defender ATP コンピューターの分離の詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **収集調査パッケージ**— ZIP ファイル内のデバイス情報を収集します。 [Microsoft Defender ATP 調査パッケージの詳細情報](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **ウイルス対策スキャンを実行**する—デバイス上で Windows Defender ウイルス対策スキャンを完全に実行します。
- **開始調査**: デバイスの[自動調査](mtp-autoir.md)を開始します。
- **アプリの実行を制限**する-デバイスに制限を設定して、Microsoft が発行した証明書で署名されたファイルのみを実行できるようにします。 [Microsoft Defender ATP を使用したアプリの制限について](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>ファイルに対するアクション
このオプションを選択すると、 **Quarantine file** `SHA1` `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` クエリ結果の、、、または列のファイルに [ファイルの検疫] アクションを適用することができます。 この操作は、現在の場所からファイルを削除し、そのコピーを検疫に配置します。

#### <a name="actions-on-users"></a>ユーザーに対するアクション
このチェックボックスをオンにすると、クエリ結果の、、または列にあるユーザーに対して [侵害済みの**ユーザーとしてマーク**] の操作が実行され `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` ます。 この操作によって、Azure Active Directory でユーザーのリスクレベルが "高" に設定され、対応する[id 保護ポリシー](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)がトリガーされます。

> [!NOTE]
> カスタム検出ルールのアクションの許可またはブロックは、現在、Microsoft の脅威保護ではサポートされていません。

### <a name="5-set-the-rule-scope"></a>5. ルールの範囲を設定します。
ルールに含まれるデバイスを指定するようにスコープを設定します。 この範囲は、デバイスをチェックするルールに影響し、メールボックスとユーザーアカウントまたは id のみをチェックするルールには影響しません。

スコープを設定するときは、次のオプションを選択できます。

- すべてのデバイス
- 特定のデバイスグループ

範囲内のデバイスからのデータのみが照会されます。 また、アクションはこれらのデバイスでのみ実行されます。

### <a name="6-review-and-turn-on-the-rule"></a>6. ルールを確認し、オンにします。
ルールを確認した後、[**作成**] をクリックして保存します。 カスタム検出ルールが直ちに実行されます。 この動作は、構成された頻度に基づいて、一致をチェックし、通知を生成し、応答アクションを実行することによって再度実行します。

## <a name="manage-existing-custom-detection-rules"></a>既存のカスタム検出ルールを管理する
既存のカスタム検出ルールの一覧を表示し、以前の実行をチェックして、トリガーされた通知を確認できます。 また、必要に応じてルールを実行して変更することもできます。

### <a name="view-existing-rules"></a>既存のルールを表示する

既存のカスタム検出ルールをすべて表示**するには**、[カスタム検出の検索] に移動し  >  **Custom detections**ます。 ページには、次の実行情報を含むすべてのルールの一覧が表示されます。

- [**前回の実行**]-ルールが最後に実行されたときに、クエリの一致をチェックし、通知を生成する
- **最終実行状態**—ルールが正常に実行されたかどうか
- **次回の実行**-次のスケジュールされた実行
- **状態**: ルールが有効になっているかどうか

### <a name="view-rule-details-modify-rule-and-run-rule"></a>ルールの詳細、変更ルール、および実行ルールを表示する

カスタム検出ルールについての包括的な情報を表示するには、[カスタム検出を**探す**] のルールの名前を選択し  >  **Custom detections**ます。 これにより、カスタム検出ルールに関するページが、アラート、実行状態、およびスコープの詳細を含む、ルールに関する一般的な情報を使用して開きます。 また、トリガーされた通知とトリガーされたアクションのリストも表示します。

![カスタム検出ルールの詳細ページ](../../media/custom-detection-details.png)<br>
*カスタム検出ルールの詳細*

このページでは、ルールに対して次の操作を実行することもできます。

- **Run** -ルールを直ちに実行します。 これにより、次の実行の間隔もリセットされます。
- **編集**—クエリを変更せずにルールを変更する
- **クエリの変更**-高度な検索でクエリを編集する
- **オン**  / **オフ**—ルールを有効にするか、または実行を停止します。
- **削除**—ルールをオフにして削除する

### <a name="view-and-manage-triggered-alerts"></a>トリガーされた通知の表示と管理

[仕分けルールの詳細]**Hunting**画面 (  >  **ユーザー設定の検出**を探し  >  ている場合) で、[トリガーされた**通知****]** に移動して、ルールに一致することによって生成された通知の一覧を表示します。 そのアラートに関する詳細情報を表示するアラートを選択し、そのアラートに対して次の処理を実行します。

- 状態と分類 (true または false のアラート) を設定してアラートを管理する
- 警告をインシデントにリンクする
- 高度な検索で警告をトリガーしたクエリを実行する

### <a name="review-actions"></a>アクションを確認する
[ルールの詳細] 画面**Hunting**(  >  [**ユーザー設定の検出**を探して  >  います **]**) で、[トリガーされた**アクション**] に移動して、ルールへの一致に基づいて実行されたアクションのリストを表示します。

>[!TIP]
>テーブル内のアイテムに関する情報をすばやく表示し、アクションを実行するには、表の左側にある選択列 [&#10003;] を使用します。

## <a name="related-topic"></a>関連トピック
- [カスタム検出の概要](custom-detections-overview.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [高度な捜索のクエリ言語について学習する](advanced-hunting-query-language.md)