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
ms.openlocfilehash: e491e6d093396e54983e96eb1ca96c5e713565ba
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089178"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのチュートリアルとシミュレーション

Microsoft Defender for Businessの設定が完了したばかりの場合は、Defender for Business のしくみをどこから確認したらいいか疑問に思うかもしれません。 この記事では、試すシナリオと、Defender for Business で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business が会社でどのように機能するかを確認するのに役立ちます。


## <a name="try-these-scenarios"></a>これらのシナリオを試す

次の表は、Defender for Business を試すいくつかのシナリオをまとめたものです。

| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード     | Defender for Business では、各デバイスでダウンロードして実行するスクリプトを使用して、デバイスのWindowsとmacOSをオンボードできます。 このスクリプトは、Azure Active Directory (Azure AD) を使用して信頼を作成し (その信頼がまだ存在しない場合)、デバイスを Microsoft Intune (Intuneがある場合) に登録し、デバイスを Defender for Business にオンボードします。 詳細については、「[デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)」を参照してください。         |
| Microsoft エンドポイント マネージャー管理センターを使用してデバイスをオンボードする     | Defender for Business を取得する前に既にIntuneを使用していた場合は、引き続きエンドポイント マネージャー管理センターを使用してデバイスをオンボードできます。 Microsoft Intuneを使用して、Windows、macOS、iOS、Android デバイスをオンボードしてみてください。 詳細については、「[Microsoft Intuneでのデバイス登録](/mem/intune/enrollment/device-enrollment)」を参照してください。        |
| セキュリティ ポリシーを編集する     | Defender for Business でセキュリティ ポリシーを管理している場合は、 **デバイス構成** ページを使用してポリシーを表示し、必要に応じてポリシーを編集します。 Defender for Business には、推奨設定を使用して会社のデバイスがオンボードされるとすぐにセキュリティで保護される既定のポリシーが付属しています。 既定のポリシーを保持し、編集し、ビジネス ニーズに合わせて独自のポリシーを定義できます。 詳細については、「[Microsoft Defender for Businessでポリシーを表示または編集](mdb-view-edit-policies.md)する」を参照してください。        |
| シミュレートされた攻撃を実行する   | Defender for Business では、いくつかのチュートリアルとシミュレーションを利用できます。 これらのチュートリアルとシミュレーションは、Defender for Business の脅威保護機能が会社でどのように機能するかを直接示すために設計されています。 シミュレートされた攻撃をチームのトレーニング演習として使用することもできます。 1 つ以上のチュートリアルを試すには、「[Microsoft Defender for Businessに推奨されるチュートリアル」を](#recommended-tutorials-for-defender-for-business)参照してください。         |
| Microsoft 365 Lighthouseでインシデントを表示する     | Microsoft 365 Lighthouseを使用している[Microsoft クラウド ソリューション プロバイダー](/partner-center/enrolling-in-the-csp-program)の場合は、Microsoft 365 Lighthouse ポータルで顧客のテナント間のインシデントを表示できます。 詳細については、「[Microsoft 365 LighthouseとMicrosoft Defender for Business](mdb-lighthouse-integration.md)」を参照してください。       |


## <a name="recommended-tutorials-for-defender-for-business"></a>Defender for Business の推奨チュートリアル

次の表では、Defender for Business のお客様に推奨されるチュートリアルについて説明します。

| チュートリアル  | 説明  |
|---------|---------|
| **ドキュメントがバックドアを削除する**     | テスト デバイスにファイルベースのマルウェアを導入する攻撃をシミュレートします。 このチュートリアルでは、シミュレーション ファイルを取得して使用する方法と、Microsoft 365 Defender ポータルで監視する内容について説明します。 <br/><br/>このチュートリアルでは、Microsoft Wordをテスト デバイスにインストールする必要があります。   |
| **ライブ応答のチュートリアル**     | Live Response で基本コマンドと高度なコマンドを使用する方法について説明します。 疑わしいファイルを見つけ、ファイルを修復し、デバイス上の情報を収集する方法について説明します。   |
| **脅威&脆弱性管理 (コア シナリオ)**     | 次の 3 つのシナリオで脅威と脆弱性の管理について説明します。 <br/><br/>1. 会社の脅威と脆弱性の露出を減らします。 <br/>2. 修復を要求します。 <br/>3. セキュリティに関する推奨事項の例外を作成します。 <br/><br/> 脅威と脆弱性の管理では、エンドポイントの脆弱性と構成ミスの検出、優先順位付け、修復にリスクベースのアプローチを使用します。      |

各チュートリアルには、シナリオ、動作方法、操作を説明するチュートリアル ドキュメントが含まれています。

> [!TIP]
> チュートリアル ドキュメントには、Microsoft Defender for Endpointへの参照が表示されます。 この記事に記載されているチュートリアルは、Defender for Endpoint または Defender for Business のいずれかで使用できます。

## <a name="how-to-access-the-tutorials"></a>チュートリアルにアクセスする方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウの [ **エンドポイント**] で、[チュートリアル] を選択 **します**。

3. 次のいずれかのチュートリアルを選択します。

   - **ドキュメントがバックドアを削除する**
   - **ライブ応答のチュートリアル**
   - **脅威&脆弱性管理 (コア シナリオ)**

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)
- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)