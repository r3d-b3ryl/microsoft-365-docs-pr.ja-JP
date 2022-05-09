---
title: エージェントの正常性に関する問題の調査
description: mdatp health コマンドの実行時に返される値について説明します
keywords: mdatp 正常性、コマンド、正常性、状態、コマンド、オンボード状態
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 13407c78f89058efe15ed0f5d8f23272716e0237
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61937366"
---
# <a name="investigate-agent-health-issues"></a>エージェントの正常性に関する問題の調査

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

次の表に、コマンドの実行時 `mdatp health` に返される値とその対応する説明を示します。

<br>

****

|値|説明|
|---|---|
|automatic_definition_update_enabled|True の自動ウイルス対策定義の更新が有効になっている場合は false、それ以外の場合は false。|
|cloud_automatic_sample_submission_consent|現在のサンプル提出レベル。 次のどちらかの値にすることができます。 <ul><li>**なし**: 疑わしいサンプルは Microsoft に送信されません。</li><li>**セーフ**: 個人を特定できる情報 (PII) を含まない疑わしいサンプルのみが自動的に送信されます。 これは、この設定の既定値です。</li><li>**すべて**: 疑わしいサンプルはすべて Microsoft に送信されます。</li></ul>|
|cloud_diagnostic_enabled|True の場合は省略可能な診断データ収集が有効です。それ以外の場合は false。 Defender for Endpoint およびその他の製品およびサービス (Microsoft Defender ウイルス対策やWindowsなど) に関連する詳細については、[Microsoft のプライバシーに関する声明を](https://go.microsoft.com/fwlink/?linkid=827576)参照してください。|
|cloud_enabled|True クラウド配信保護が有効になっている場合は false、それ以外の場合は false。|
|conflicting_applications|Microsoft Defender for Endpointと競合している可能性があるアプリケーションの一覧。 この一覧には、互換性の問題の原因として知られている他のセキュリティ製品やその他のアプリケーションが含まれますが、これらに限定されません。|
|definitions_status|ウイルス対策定義の状態。|
|definitions_updated|最後のウイルス対策定義更新の日時。|
|definitions_updated_minutes_ago|最後のウイルス対策定義の更新後の分数。|
|definitions_version|ウイルス対策定義のバージョン。|
|edr_client_version|デバイスで実行されているEDR クライアントのバージョン。|
|edr_configuration_version|EDR構成バージョン。|
|edr_device_tags|デバイスに関連付けられているタグの一覧。|
|edr_group_ids|デバイスが関連付けられているグループ ID。|
|edr_machine_id|Microsoft 365 Defenderで使用されるデバイス識別子。|
|engine_version|ウイルス対策エンジンのバージョン。|
|健康|製品が正常な場合は True、それ以外の場合は false。|
|ライセンス|デバイスがテナントにオンボードされている場合は True、それ以外の場合は false。|
|log_level|製品の現在のログ レベル。|
|machine_guid|ウイルス対策コンポーネントによって使用される一意のマシン識別子。|
|network_protection_status|ネットワーク保護コンポーネントの状態 (macOS のみ)。 次のどちらかの値にすることができます。 <ul><li>**開始** - ネットワーク保護が開始されています</li><li>**failed_to_start** - エラーが原因でネットワーク保護を開始できませんでした</li><li>**開始済み** - デバイスでネットワーク保護が現在実行されている</li><li>**再起動** - ネットワーク保護は現在再起動中です</li><li>**停止** - ネットワーク保護が停止している</li><li>**停止** - ネットワーク保護が実行されていない</li></ul>|
|org_id|デバイスをオンボードする組織。 デバイスがまだ組織にオンボードされていない場合は、使用できません。 オンボードの詳細については、「[Microsoft Defender for Endpointにオンボードする」を](onboarding.md)参照してください。|
|passive_mode_enabled|True ウイルス対策コンポーネントがパッシブ モードで実行するように設定されている場合は false、それ以外の場合は false。|
|product_expiration|現在の製品バージョンがサポート終了に達した日付と時刻。|
|real_time_protection_available|True の場合、リアルタイム保護コンポーネントが正常です。それ以外の場合は false。|
|real_time_protection_enabled|True の場合はリアルタイムウイルス対策保護が有効です。それ以外の場合は false。|
|real_time_protection_subsystem|リアルタイム保護に使用されるサブシステム。 リアルタイム保護が期待どおりに動作しない場合、この出力は使用できません。|
|release_ring|リリース リング。 詳細については、「 [デプロイ リング」を](deployment-rings.md)参照してください。|
|
