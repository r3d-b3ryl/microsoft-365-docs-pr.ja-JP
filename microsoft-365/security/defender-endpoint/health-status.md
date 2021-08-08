---
title: エージェントの正常性に関する問題の調査
description: mdatp 正常性コマンドを実行するときに返される値について説明します。
keywords: mdatp の正常性、コマンド、正常性、状態、コマンド、オンボーディングの状態
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: db3f9f7b54e14fbe198a7ae2dd06b76541d0c141322840cb2c91c575147d6195
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53890457"
---
# <a name="investigate-agent-health-issues"></a>エージェントの正常性に関する問題の調査

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


次の表に、コマンドの実行時に返される値と、それに対応する `mdatp health` 説明を示します。

| 値 | 説明 |
|-|-|
| automatic_definition_update_enabled | True の場合は、自動ウイルス対策定義の更新プログラムが有効になっている場合は false。それ以外の場合は false。 |
|  cloud_automatic_sample_submission_consent | 現在のサンプル申請レベル。 次のどちらかの値にすることができます。     <br><br>  - **なし**: 疑わしいサンプルは Microsoft に送信されません。  <br> <br>     - **セーフ**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。 これは、この設定の既定値です。    <br> <br>   - **All**: すべての疑わしいサンプルが Microsoft に送信されます。   |
| cloud_diagnostic_enabled | オプションの診断データ収集が有効な場合は True、それ以外の場合は false。 Defender for Endpoint および他の製品およびサービス (Microsoft Defender ウイルス対策 および Windows 10に関する詳細については[、「Microsoft Privacy Statement」を参照してください](https://go.microsoft.com/fwlink/?linkid=827576)。 |
| cloud_enabled | True の場合は、クラウド配信の保護が有効になっている場合、それ以外の場合は false。 |
| conflicting_applications | Microsoft Defender for Endpoint と競合している可能性があるアプリケーションの一覧。 このリストには、互換性の問題が発生することが知られている他のセキュリティ製品や他のアプリケーションが含まれますが、これらに限定されません。 |
| definitions_status | ウイルス対策定義の状態。 |
| definitions_updated | 最後のウイルス対策定義更新の日時。 |
| definitions_updated_minutes_ago | 前回のウイルス対策定義の更新後の分数。 |
| definitions_version | ウイルス対策定義のバージョン。 |
| edr_client_version | デバイスで実行EDRクライアントのバージョン。 |
| edr_configuration_version | EDRバージョンを指定します。 |
| edr_device_tags | デバイスに関連付けられているタグの一覧。 |
| edr_group_ids | デバイスが関連付けられているグループ ID。 |
| edr_machine_id | デバイスで使用されるデバイスMicrosoft Defender セキュリティ センター。 |
| engine_version | ウイルス対策エンジンのバージョン。 |
| 正常 | 製品が正常な場合は True、それ以外の場合は false。 |
| ライセンス | True の場合は、デバイスがテナントにオンボードされ、それ以外の場合は false。 |
| log_level | 製品の現在のログ レベル。 |
| machine_guid | ウイルス対策コンポーネントで使用される一意のコンピューター識別子。 |
| network_protection_status                 | ネットワーク保護コンポーネントの状態 (macOS のみ)。 次のどちらかの値にすることができます。       <br> <br>- **starting** - ネットワーク保護が開始されています  <br> <br>     - **failed_to_start** - エラーが原因でネットワーク保護を開始できなかった   <br> <br>    - **開始** - ネットワーク保護が現在デバイスで実行されている     <br> <br>  - **再起動 -** ネットワーク保護が現在再起動中   <br> <br>    - **停止 -** ネットワーク保護が停止している     <br> <br>  - **停止 -** ネットワーク保護が実行されていない |
| org_id | デバイスがオンボードされている組織。 デバイスがまだ組織にオンボードされていない場合、この印刷は使用できません。 オンボーディングの詳細については [、「Onboard to Microsoft Defender for Endpoint」を参照してください](onboarding.md)。 |
| passive_mode_enabled | True を指定すると、ウイルス対策コンポーネントがパッシブ モードで実行されます。それ以外の場合は false。 |
| product_expiration | 現在の製品バージョンがサポート終了に達した日時。 |
| real_time_protection_available | リアルタイム保護コンポーネントが正常な場合は True、それ以外の場合は false。 |
| real_time_protection_enabled | True の場合は、リアルタイムのウイルス対策保護が有効になっている場合、それ以外の場合は false。 |
| real_time_protection_subsystem | リアルタイム保護を提供するために使用されるサブシステム。 リアルタイム保護が期待通り動作しない場合、この印刷は使用できません。 |
| release_ring | リングを解放します。 詳細については、「展開リング   [」を参照してください](deployment-rings.md)。 |