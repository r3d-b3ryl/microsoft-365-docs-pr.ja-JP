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
ms.openlocfilehash: e1806a0a21dc5f3fc300442f31da5016ffcf99e7
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215273"
---
# <a name="device-profiles"></a>デバイス プロファイル

デバイスに異なる事前設定構成 ("デバイス プロファイル") を割り当て、各構成を特定の種類のユーザーのニーズに合って最適化できます。 次の 3 つのデバイス プロファイルを使用できます。

- Standard
- 機密データ
- Power User

デバイス プロファイルは、デバイス構成オプションの階層の一部と考えられます。

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="ピラミッドとして表示されるデバイス構成。説明は次のとおりです。":::

基本的に、Microsoft マネージド デスクトップデバイスには、標準のセキュリティ 基準、コンプライアンス ポリシー、更新プログラムの設定、およびグループWindows基盤があります。 この機能をMicrosoft マネージド デスクトップ、すべてのデバイスにこれらの要素が含まれる必要があります。この要素は、管理者が変更を要求せずに変更Microsoft マネージド デスクトップ。

デバイス プロファイルは、次の上位レベルに表示されます。 すべてのデバイスMicrosoft マネージド デスクトップ 1 つのプロファイル (および 1 つのみ) プロファイルが割り当てられている必要があります。 管理者は、デバイスが割り当てられているプロファイルを選択できます。

さらに高いレベルでは、追加 [のカスタマイズがあります](customizing.md)。 各デバイスには、1 つ以上のカスタマイズ (またはなし) を設定できます。 下位レベルのレイヤー (デバイス プロファイルまたは基礎構成) を変更するか、標準構成の上に層を重ね合った完全に新しい要求にすることもできます。

上部には、ネットワークの詳細やアプリケーションなど、独自の変更があります。 デバイスは、これらの変更を任意の数持つ可能性があります。この変更は、デバイスによって管理またはブロックMicrosoft マネージド デスクトップ。


## <a name="device-profile-details"></a>デバイス プロファイルの詳細

次の表は、デバイス プロファイルによって構成された各設定の設定とその既定値をまとめたものです。 (これらの設定は、ユーザー設定OMA-URIsカスタム構成プロファイルを使用して構成Microsoft エンドポイント マネージャー)。

<br>

****

|特徴|機密データ|Power User|Standard|
|---|:---:|:---:|:---:|
|**外部ファイルのブロックStorage**|はい|はい|いいえ|
|**[クラウド ブロック レベル](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|高|高|高|
|**Microsoft アカウントを無効にする**|はい|はい|いいえ|
|**個人用アカウントを無効OneDrive**|はい|はい|いいえ|
|**昇格のためのデスクトップのセキュリティ保護に切り替える**|いいえ|はい|いいえ|
|**Microsoft Defender for Endpoint Device Tag**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**デバイスの管理者**|いいえ|はい|いいえ|
|**Autopilot プロファイル**|MMD 標準|MMD Power User|MMD 標準|
|**AppLocker**|はい|いいえ|いいえ|
|**パブリック ストアのブロック**|はい|はい|なし|
|

各デバイス プロファイルには、次の項目も含まれます。

- 動的メンバーシップ Azure Active Directory (AAD) デバイス グループ
- 静的メンバーシップ AAD デバイス グループ
- [Microsoft エンドポイント マネージャー構成プロファイル]

> [!IMPORTANT]
> これらのグループのメンバーシップを直接変更しない。 「プロファイルの再割り当て」の説明に従 [ってインターフェイスを使用します](../working-with-managed-desktop/change-device-profile.md)。

## <a name="limitations"></a>制限事項

他のポリシーと同様に、デバイス プロファイルとその詳細に例外を要求できます。 組織の各デバイス プロファイル ("tenant") の 1 つAzure Active Directoryしてください。 たとえば、機密データ デバイス プロファイルが一部のユーザーに対して AppLocker を無効にすることを要求できない場合があります。 機密データ プロファイルを持つすべてのデバイスに同じ構成が必要です。

各デバイスは、1 つのプロファイルのみを持つ場合があります。 特定のデバイスが複数のユーザーによって使用されている場合、そのデバイス上のすべてのユーザーは同じ構成を持つ。
