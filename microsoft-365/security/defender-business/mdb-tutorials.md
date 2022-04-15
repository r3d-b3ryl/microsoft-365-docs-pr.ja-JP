---
title: Microsoft Defender for Businessのチュートリアルとシミュレーション
description: Defender for Business の使用を開始するために役立ついくつかのチュートリアルについて説明します
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 42d7acb4512928a32ac99c486a231d7891102208
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861336"
---
# <a name="tutorials-and-simulations-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのチュートリアルとシミュレーション

> [!IMPORTANT]
> Microsoft Defender for Businessはプレビュー段階にあり、[ここでサインアップ](https://aka.ms/mdb-preview)して要求する顧客と IT パートナーに段階的にロールアウトされます。 今後数週間以内に顧客とパートナーの初期セットをオンボードし、一般提供に至るまでプレビューを拡張します。 プレビューは [シナリオの初期セット](#try-these-preview-scenarios)で開始され、機能は定期的に追加されることに注意してください。
> 
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。 

Microsoft Defender for Businessの設定が完了したばかりの場合は、Defender for Business のしくみをどこから確認したらいいか疑問に思うかもしれません。 この記事では、試用するプレビュー シナリオと、Defender for Business で使用できるいくつかのチュートリアルとシミュレーションについて説明します。 これらのリソースは、Defender for Business が会社でどのように機能するかを確認するのに役立ちます。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="try-these-preview-scenarios"></a>これらのプレビュー シナリオを試す

次の表は、Defender for Business を試すいくつかのシナリオをまとめたものです。

| シナリオ  | 説明  |
|---------|---------|
| ローカル スクリプトを使用したデバイスのオンボード <br/>(*運用環境のデプロイ用ではありません*)     | Defender for Business では、各デバイスでダウンロードして実行するスクリプトを使用して、最大 10 台のWindows 10 デバイスと 11 台のデバイスをオンボードできます。 Defender for Business が環境でどのように動作するかを評価するのに適したスクリプトは、Azure Active Directory (Azure AD) との信頼関係を作成し、デバイスをMicrosoft Intuneに登録します。 詳細については、「[デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)」を参照してください。         |
| Microsoft Intuneを使用してデバイスをオンボードする     | Defender for Endpoint を取得する前にMicrosoft Intuneを既に使用していた場合は、引き続きMicrosoft Intuneを使用してデバイスをオンボードできます。 Microsoft Intuneを使用して macOS、iOS、Android デバイスをオンボードしてみてください。 詳細については、「[Microsoft Intuneでのデバイス登録](/mem/intune/enrollment/device-enrollment)」を参照してください。        |
| セキュリティ ポリシーを編集する     | Defender for Business でセキュリティ ポリシーを管理している場合は、 **デバイス構成** ページを使用してポリシーを表示および編集します。 詳細については、「[Microsoft Defender for Businessでポリシーを表示または編集](mdb-view-edit-policies.md)する」を参照してください。        |
| シミュレートされた攻撃を実行する   | Defender for Business では、いくつかのチュートリアルとシミュレーションを利用できます。 これらのチュートリアルとシミュレーションは、Defender for Business の脅威保護機能が会社でどのように機能するかを直接示すために設計されています。 1 つ以上のチュートリアルを試すには、「[Microsoft Defender for Businessに推奨されるチュートリアル」を](#recommended-tutorials-for-defender-for-business)参照してください。         |
| Microsoft 365 Lighthouseでインシデントを表示する     | Microsoft 365 Lighthouseを使用している[Microsoft クラウド ソリューション プロバイダー](/partner-center/enrolling-in-the-csp-program)の場合は、Microsoft 365 Lighthouse ポータルで顧客のテナント間でインシデントをすぐに表示できます。 詳細については、「[Microsoft 365 LighthouseとMicrosoft Defender for Business](mdb-lighthouse-integration.md)」を参照してください。       |


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