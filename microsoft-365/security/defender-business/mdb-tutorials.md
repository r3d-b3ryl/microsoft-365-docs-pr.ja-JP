---
title: Microsoft Defender for Business のチュートリアルとシミュレーション
description: Defender for Business の使用を始めるのに役立ついくつかのチュートリアルについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: cfb98e3276025fbd9c75466de3c82339243e2f3b
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375316"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Business のチュートリアルとシミュレーション

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business のセットアップが完了したばかりの場合は、Defender for Business の動作についてどこから学ぶのか疑問に思う場合があります。 この記事では、試すプレビュー シナリオと、Defender for Business で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business が会社でどのように機能できるのか確認するために設計されています。

## <a name="try-these-preview-scenarios"></a>これらのプレビュー シナリオを試す

次の表は、Defender for Business のプレビュー中に試すシナリオの概要を示しています。 
<br/><br/>


| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード     | Defender for Business では、各デバイスWindows 10実行するスクリプトを使用して、デバイスと 11 台のデバイスをオンボードできます。 スクリプトは、ユーザー (Azure Active Directory) とのAzure ADを作成し、デバイスを Microsoft Intune。 詳細については [、「Defender for Business でローカル スクリプトを使用してデバイスをオンボードする」を参照してください](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business)。         |
| デバイスを使用したオンボード Microsoft Intune     | Defender for Endpoint を取得する前Microsoft Intuneを既に使用していた場合は、Microsoft Intuneデバイスをオンボードできます。 macOS、iOS、Linux、および Android デバイスのオンボーディングを試Microsoft Intune。 詳細については、「デバイスの[登録」を参照Microsoft Intune。](/mem/intune/enrollment/device-enrollment)        |
| セキュリティ ポリシーと設定の編集     | Defender for Business でセキュリティ ポリシーと設定を管理している場合は、[デバイス構成] ページを使用してポリシーを表示および編集します。 詳細については [、「Microsoft Defender for Business のポリシーを表示または編集する」を参照してください](mdb-view-edit-policies.md)。        |
| シミュレートされた攻撃を実行する   | Defender for Business では、いくつかのチュートリアルとシミュレーションを使用できます。 これらのチュートリアルとシミュレーションは、Defender for Business の脅威保護機能が会社でどのように機能できるのか、直接説明するように設計されています。 1 つ以上のチュートリアルを試す場合は、「Microsoft Defender for Business の推奨 [チュートリアル」を参照してください](#recommended-tutorials-for-defender-for-business)。         |
| [インシデントの表示] Microsoft 365 Lighthouse     | Microsoft パートナーがサービス を使用している場合Microsoft 365 Lighthouseポータルで顧客のテナント間のインシデントをMicrosoft 365 Lighthouseできます。 詳細については、「microsoft Defender [for Business Microsoft 365 Lighthouse」を参照してください](mdb-lighthouse-integration.md)。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business の推奨チュートリアル

次の表に、Defender for Business のお客様に推奨されるチュートリアルを示します。
<br/><br/>


| チュートリアル  | 説明  |
|---------|---------|
| **ドキュメントドロップバックドア**     | テスト デバイスにファイル ベースのマルウェアを導入する攻撃をシミュレートします。 チュートリアルでは、シミュレーション ファイルを取得して使用する方法と、シミュレーション ポータルで何を監視Microsoft 365 Defenderします。 <br/><br/>このチュートリアルでは、Microsoft Wordデバイスにインストールする必要があります。   |
| **ライブ応答のチュートリアル**     | Live Response で基本コマンドと高度なコマンドを使用する方法について説明します。 不審なファイルを見つけ、ファイルを修復し、デバイス上の情報を収集する方法について学習します。   |
| **脅威&の管理 (コア シナリオ)**     | 次の 3 つの脅威と脆弱性の管理の詳細について説明します。 <br/><br/>1. 組織の脅威と脆弱性の暴露を減らします。 <br/>2. 修復を要求します。 <br/>3. セキュリティに関する推奨事項の例外を作成します。 <br/><br/> 脅威と脆弱性の管理は、エンドポイントの脆弱性と誤った構成の検出、事前設定、および修復にリスクベースのアプローチを使用します。      |

各チュートリアルには、シナリオ、動作方法、および実行方法を説明するチュートリアル ドキュメントが含まれています。

> [!TIP]
> チュートリアル ドキュメントには、Microsoft Defender for Endpoint への参照が表示されます。 この記事に記載されているチュートリアルは、Defender for Endpoint または Defender for Business で使用できます。

## <a name="how-to-access-the-tutorials"></a>チュートリアルにアクセスする方法

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウの [エンドポイント] で **、[チュートリアル**] **を選択します**。

3. 次のいずれかのチュートリアルを選択します。

   - **ドキュメントドロップバックドア**
   - **ライブ応答のチュートリアル**
   - **脅威&の管理 (コア シナリオ)**

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business でデバイスを管理する](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)