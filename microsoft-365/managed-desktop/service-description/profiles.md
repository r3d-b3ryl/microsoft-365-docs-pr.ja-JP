---
title: デバイス プロファイルについて
description: 管理者がデバイスに割り当てできるさまざまなプロファイル
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691276"
---
# <a name="device-profiles"></a>デバイス プロファイル

デバイスに異なる事前設定構成 ("デバイス プロファイル") を割り当て、各構成を特定の種類のユーザーのニーズに合って最適化できます。 次の 3 つのデバイス プロファイルを使用できます。

- 標準
- 機密データ
- Power User

デバイス プロファイルは、デバイス構成オプションの階層の一部と考えられます。

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="ピラミッドとして表示されるデバイス構成。説明は次のとおりです。":::

基本的に、すべての Microsoft Managed Desktop デバイスには、標準のセキュリティ 基準、コンプライアンス ポリシー、Windows Update 設定、およびグループを含む基盤があります。 Microsoft Managed Desktop を使用するには、すべてのデバイスにこれらすべての要素が含まれる必要があります。これは、Microsoft Managed Desktop への要求なしに管理者が変更することはできません。

デバイス プロファイルは、次の上位レベルに表示されます。 すべての Microsoft Managed Desktop デバイスには、1 つのプロファイル (および 1 つのみ) プロファイルが割り当てられている必要があります。 管理者は、デバイスが割り当てられているプロファイルを選択できます。

さらに高いレベルでは、追加 [のカスタマイズがあります](customizing.md)。 各デバイスには、1 つ以上のカスタマイズ (またはなし) を設定できます。 下位レベルのレイヤー (デバイス プロファイルまたは基礎構成) を変更するか、標準構成の上に層を重ね合った完全に新しい要求にすることもできます。

上部には、ネットワークの詳細やアプリケーションなど、独自の変更があります。 デバイスには、Microsoft Managed Desktop によって管理またはブロックされない、これらの変更を任意の数に設定できます。


## <a name="device-profile-details"></a>デバイス プロファイルの詳細

次の表は、デバイス プロファイルによって構成された各設定の設定とその既定値をまとめたものです。 (これらの設定は、Microsoft Endpoint Manager のカスタム構成プロファイルOMA-URIsを使用して構成されます)。

| 機能 | 機密データ | Power User | 標準 |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **外部ストレージのブロック**                                                                                                                               | はい                       | はい                   | いいえ                   |
| **[クラウド ブロック レベル](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | 高い                      | 高い                  | 高い                 |
| **Microsoft アカウントを無効にする**                                                                                                                           | はい                       | はい                   | いいえ                   |
| **個人用 OneDrive を無効にする**                                                                                                                            | はい                       | はい                   | いいえ                   |
| **昇格のためのデスクトップのセキュリティ保護に切り替える**                                                                                                               | いいえ                        | はい                   | いいえ                   |
| **Microsoft Defender for Endpoint Device Tag**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **デバイスの管理者**                                                                                                                                 | いいえ                        | はい                   | いいえ                   |
| **Autopilot プロファイル**                                                                                                                                     | MMD 標準               | MMD Power User         | MMD 標準          |
| **AppLocker**                                                                                                                                            | はい                       | いいえ                    | いいえ                   |
| **パブリック ストアのブロック**                                                                                                                                   | はい                       | はい                   | いいえ                   |

各デバイス プロファイルには、次の項目も含まれます。

- 動的メンバーシップ Azure Active Directory (AAD) デバイス グループ
- 静的メンバーシップ AAD デバイス グループ
- Microsoft Endpoint Manager 構成プロファイル

> [!IMPORTANT]
> これらのグループのメンバーシップを直接変更しない。 「プロファイルの再割り当て」の説明に従 [ってインターフェイスを使用します](../working-with-managed-desktop/change-device-profile.md)。

## <a name="limitations"></a>制限事項

他のポリシーと同様に、デバイス プロファイルとその詳細に例外を要求できます。 Azure Active Directory 組織 ("tenant") には、各デバイス プロファイルの 1 つしか持てない場合があります。 たとえば、機密データ デバイス プロファイルが一部のユーザーに対して AppLocker を無効にすることを要求できない場合があります。 機密データ プロファイルを持つすべてのデバイスに同じ構成が必要です。

各デバイスは、1 つのプロファイルのみを持つ場合があります。 特定のデバイスが複数のユーザーによって使用されている場合、そのデバイス上のすべてのユーザーは同じ構成を持つ。
