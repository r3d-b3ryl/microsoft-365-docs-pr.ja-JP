---
title: デバイス プロファイルについて
description: 管理者がデバイスに割り当てできるさまざまなプロファイル
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: d12a197db8dbcb6356882082c212754fef726d4e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320831"
---
# <a name="device-profiles"></a>デバイス プロファイル

デバイス プロファイルは、デバイス構成オプションの階層の一部と考えられます。

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="ピラミッドとして表示されるデバイス構成。説明は次のとおりです。":::

| デバイス構成オプション | 説明
| ----- | ----- |
| 構成 | 上部には、ネットワークの詳細やアプリケーションなど、独自の構成があります。 デバイスには、Microsoft Managed Desktop によって管理またはブロックされない、任意の数の構成を使用できます。 |
| カスタマイズ | 次の上位レベルは、追加 [のカスタマイズです](customizing.md)。 各デバイスには、1 つ以上のカスタマイズ (またはなし) を設定できます。 カスタマイズは、下位レベルのレイヤー (デバイス プロファイルまたは基礎構成) を変更するか、標準構成の上に層化された完全に新しい要求になります。 |
| デバイス プロファイル | すべての Microsoft Managed Desktop デバイスには、割り当てられているプロファイルが 1 つで、1 つしか割り当てられていない必要があります。 管理者は、デバイスが割り当てられているプロファイルを選択できます。<br><br>デバイスに異なる事前設定プロファイルを割り当てできます。 各プロファイルは、特定の種類のユーザーのニーズに合って最適化されています。 次の 3 つのデバイス プロファイルを使用できます。<ul><li>Standard</li><li>機密データ</li><li>Power User</li> |
| Foundation | 基本的に、すべての Microsoft Managed Desktop デバイスには、以下を含む基盤があります。<br><ul><li>標準のセキュリティ基準</li><li>コンプライアンス ポリシー</li><li>Windows更新の設定</li><li>グループ</li></ul><br>Microsoft Managed Desktop を使用するには、すべてのデバイスにこれらすべての要素が含まれる必要があります。 これらの要素は、管理者が変更することはできません。 Microsoft Managed Desktop に要求を送信する必要があります。 |

## <a name="device-profile-details"></a>デバイス プロファイルの詳細

次の表は、デバイス プロファイルによって構成された各設定の設定とその既定値をまとめたものです。 これらの設定は、カスタム構成プロファイルを使用して、OMA-URIsを使用して構成Microsoft エンドポイント マネージャー。

<br>

****

| 機能 | 機密データ | Power User | Standard |
| ----- | :-----: | :-----: | :-----: |
|**外部ファイルをブロックStorage**| はい | はい | いいえ |
|**[クラウド ブロック レベル](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)**| 高 | 高 | 高 |
|**Microsoft アカウントを無効にする**| はい | はい | いいえ |
|**個人用アカウントを無効OneDrive**| はい | はい | いいえ |
|**[昇格のためのデスクトップのセキュリティ保護に切り替える](/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-useraccountcontrol-switchtothesecuredesktopwhenpromptingforelevation)**| いいえ | はい | いいえ |
|**Microsoft Defender for Endpoint Device Tag**| M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
|**デバイスの管理者**| いいえ | はい | いいえ |
|**Autopilot プロファイル**| MMD 標準 | MMD Power User | MMD 標準 |
|**AppLocker**| はい | いいえ | いいえ |
|**パブリック ストアのブロック**| はい | はい | いいえ |
|

各デバイス プロファイルには、次の項目も含まれます。

- デバイス グループのAzure Active Directoryメンバーシップ。
- デバイス グループの静的Azure Active Directoryメンバーシップ。
- 構成Microsoft エンドポイント マネージャープロファイル。

> [!IMPORTANT]
> これらのグループのメンバーシップを直接変更しない。 「プロファイルの再割り当て」の説明に従 [ってインターフェイスを使用します](../working-with-managed-desktop/change-device-profile.md)。

## <a name="limitations"></a>制限事項

他のポリシーと同様に、デバイス プロファイルとその詳細に例外を要求できます。

各デバイス プロファイルは、組織 ("tenant") 内Azure Active Directory 1 つしか持てないというAzure Active Directory念頭に置いておきます。 たとえば、機密データ デバイス プロファイルが一部のユーザーに対して AppLocker を無効にすることを要求できない場合があります。 機密データ デバイス プロファイルを持つすべてのデバイスに同じ構成が必要です。

各デバイスは、1 つのプロファイルのみを持つ場合があります。 特定のデバイスが複数のユーザーによって使用されている場合、そのデバイス上のすべてのユーザーは同じ構成を持つ。
