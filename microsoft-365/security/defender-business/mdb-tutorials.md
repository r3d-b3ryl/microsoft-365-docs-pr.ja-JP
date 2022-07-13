---
title: Microsoft Defender for Businessのチュートリアルとシミュレーション
description: Defender for Business の使用を開始するために役立ついくつかのチュートリアルについて説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 029be738b8c916ec4eb16970ae2d2ff3c460f639
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66771976"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのチュートリアルとシミュレーション

この記事では、試すシナリオと、Defender for Business で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business が会社でどのように機能するかを示しています。


## <a name="try-these-scenarios"></a>これらのシナリオを試す

次の表は、Defender for Business を試すいくつかのシナリオをまとめたものです。

| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード     | Defender for Business では、各デバイスでダウンロードして実行するスクリプトを使用して、Windows デバイスと Mac デバイスをオンボードできます。 このスクリプトは、その信頼がまだ存在しない場合は、Azure Active Directory (Azure AD) との信頼を作成します。Intuneしている場合は、デバイスをMicrosoft Intuneに登録し、デバイスを Defender for Business にオンボードします。 詳細については、「 [Defender for Business にデバイスをオンボードする」を](mdb-onboard-devices.md)参照してください。         |
| Microsoft エンドポイント マネージャー 管理センターを使用してデバイスをオンボードする     | Defender for Business を取得する前に既にIntuneを使用していた場合は、引き続きエンドポイント マネージャー管理センターを使用してデバイスをオンボードできます。 Microsoft Intuneを使用して Windows、Mac、iOS、Android デバイスをオンボードしてみてください。 詳細については、「[Microsoft Intuneでのデバイス登録](/mem/intune/enrollment/device-enrollment)」を参照してください。        |
| セキュリティ ポリシーを編集する     | Defender for Business でセキュリティ ポリシーを管理している場合は、 **デバイス構成** ページを使用してポリシーを表示および編集します。 Defender for Business には、推奨設定を使用して会社のデバイスがオンボードされるとすぐにセキュリティで保護される既定のポリシーが付属しています。 既定のポリシーを保持し、編集し、ビジネス ニーズに合わせて独自のポリシーを定義できます。 詳細については、「 [Defender for Business のポリシーを表示または編集する」を](mdb-view-edit-policies.md)参照してください。        |
| シミュレートされた攻撃を実行する   | Defender for Business では、いくつかのチュートリアルとシミュレーションを利用できます。 これらのチュートリアルとシミュレーションでは、Defender for Business の脅威保護機能が会社でどのように機能するかを示します。 シミュレートされた攻撃をチームのトレーニング演習として使用することもできます。 チュートリアルを試すには、「 [Defender for Business の推奨チュートリアル」を](#recommended-tutorials-for-defender-for-business)参照してください。         |
| Microsoft 365 Lighthouseでインシデントを表示する     | Microsoft 365 Lighthouseを使用している [Microsoft Cloud Solution Provider](/partner-center/enrolling-in-the-csp-program) の場合は、Microsoft 365 Lighthouse ポータルで顧客のテナント間のインシデントを表示できます。 詳細については、「[Microsoft 365 Lighthouseと Defender for Business](mdb-lighthouse-integration.md)」を参照してください。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business の推奨チュートリアル

次の表では、Defender for Business のお客様に推奨されるチュートリアルについて説明します。

| チュートリアル  | 説明  |
|---------|---------|
| **ドキュメント ドロップ バックドア**     | テスト デバイスにファイルベースのマルウェアを導入する攻撃をシミュレートします。 このチュートリアルでは、シミュレーション ファイルを使用する方法と、Microsoft 365 Defender ポータルで監視する内容について説明します。 <p>このチュートリアルでは、Microsoft Word をテスト デバイスにインストールする必要があります。   |
| **ライブ応答**     | Live Response で基本コマンドと高度なコマンドを使用する方法について説明します。 疑わしいファイルを見つけ、ファイルを修復し、デバイス上の情報を収集する方法について説明します。   |
| **脅威&脆弱性管理 (コア シナリオ)**     | 次の 3 つのシナリオで脅威と脆弱性の管理について説明します。<ol><li>会社の脅威と脆弱性の露出を減らします。</li><li>修復を要求します。</li><li>セキュリティに関する推奨事項の例外を作成します。</li></ol> <p> 脅威&脆弱性管理では、エンドポイントの脆弱性と構成ミスの検出、優先順位付け、修復にリスクベースのアプローチを使用します。      |

各チュートリアルには、シナリオ、動作方法、操作を説明するチュートリアル ドキュメントが含まれています。

> [!TIP]
> チュートリアル ドキュメントには、Microsoft Defender for Endpointへの参照が表示されます。 この記事に記載されているチュートリアルは、Defender for Endpoint または Defender for Business のいずれかで使用できます。

## <a name="how-to-access-the-tutorials"></a>チュートリアルにアクセスする方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウの [ **エンドポイント**] で、[チュートリアル] を選択 **します**。

3. 次のいずれかのチュートリアルを選択します。

   - **ドキュメント ドロップ バックドア**
   - **ライブ応答**
   - **脅威&脆弱性管理 (コア シナリオ)**

## <a name="next-steps"></a>次の手順

- [Defender for Business でデバイスを管理する](mdb-manage-devices.md)
- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)