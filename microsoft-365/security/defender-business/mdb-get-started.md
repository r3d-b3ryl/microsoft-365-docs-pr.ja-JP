---
title: Microsoft Defender for Business の使用を開始する (プレビュー)
description: ポータルの移動、状態と推奨事項の表示など、Microsoft Defender for Business (プレビュー) の使用を開始する方法を参照してください。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.custom: intro-get-started
ms.openlocfilehash: 5df69a578c5f4d3db7c366a0369e7efdbf934b79
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61904787"
---
# <a name="get-started-using-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business の使用を開始する (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

会社のセットアップと構成プロセスが完了したら、Microsoft Defender for Business (プレビュー) の使用を開始する最善の方法は、Microsoft 365 Defender ポータル ( ) にアクセスし、Microsoft 365 のユーザー アカウントでサインインする方法です。 [https://security.microsoft.com](https://security.microsoft.com) 

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="navigate-the-microsoft-365-defender-portal"></a>ポータルをMicrosoft 365 Defenderする

[Microsoft 365 Defender ポータル ( ) は、Microsoft Defender for Business (プレビュー) を使用および管理するためのワンストップ [https://security.microsoft.com](https://security.microsoft.com) ショップです。 開始に役立つウェルカム バナーと吹き出し、関連情報を表示するカード、さまざまな機能に簡単にアクセスするためのナビゲーション バーが含まれています。
 
少し時間を取って、ポータルをMicrosoft 365 Defenderしてください。

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Microsoft 365 Defender ポータル":::

## <a name="use-the-navigation-bar"></a>ナビゲーション バーを使用する

画面の左側のナビゲーション バーを使用して、インシデントへのアクセス、レポートの表示、セキュリティ ポリシーと設定の管理を行います。 次の表に、ナビゲーション バーに表示されるアイテムについて説明します。

| アイテム | 説明 |
|:---|:---|
| **ホーム** | ページのホーム ページに移動Microsoft 365 Defender。 ホーム ページには、検出されたアクティブな脅威を強調表示するカードと、会社のデータとデバイスのセキュリティ保護に役立つ推奨事項が含まれています。 <br/><br/>推奨事項は Defender for Business (プレビュー) に含まれているので、セキュリティ チームの時間と労力を節約できます。 推奨事項は、業界のベスト プラクティスに基づいて行います。 推奨事項の詳細については、「セキュリティの推奨事項 - 脅威と脆弱性の管理」[を参照してください](../defender-endpoint/tvm-security-recommendation.md)。 |
| **インシデント** | 最近のインシデントの一覧にアクセスします。 アラートがトリガーされると、インシデントが作成されます。 インシデントには、複数のアラートを含めできます。 インシデントを定期的に確認してください。 <br/><br/>インシデントの詳細については、「Microsoft Defender for Business でのインシデントの表示と管理 [(プレビュー)」を参照してください](mdb-view-manage-incidents.md)。|
| **アクション センター** | 完了または保留中のアクションを含む、応答アクションの一覧にアクセスします。 <br/>- [履歴] **タブを** 選択して、実行されたアクションを表示します。 一部のアクションは自動的に実行されます。他のユーザーは、承認された後に手動で実行または完了します。 <br/>- [ **保留中] タブを** 選択して、続行する承認が必要なアクションを表示します。 <br/><br/>アクション センターの詳細については、「アクション センターで [修復アクションを確認する」を参照してください](mdb-review-remediation-actions.md)。 |
| **脅威の分析** | 現在の脅威のビューにアクセスし、脅威の状況を一目で確認できます。 脅威分析には、Microsoft セキュリティ研究者からのレポートや情報も含まれています。 <br/><br/>脅威分析の詳細については、「脅威分析による新たな脅威の追跡と対応」 [を参照してください](../defender-endpoint/threat-analytics.md)。 |
| **セキュア スコア** | 会社のセキュリティの位置を示す情報を提供し、改善するための提案を提供します。<br/><br/>Secure Score の詳細については [、「Microsoft Secure Score for Devices」を参照してください](../defender-endpoint/tvm-microsoft-secure-score-devices.md)。 |
| **ラーニング ハブ** | サブスクリプションに含まれるラーニング パスを使用して、セキュリティ トレーニングや他のリソースにアクセスできます。 製品、スキル レベル、役割などによってフィルター処理できます。 ラーニング ハブは、セキュリティ チームが Defender for Business (プレビュー) のセキュリティ機能 & 機能や[、Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)や Microsoft Defender for Office 365 などの Microsoft 製品を強化するのに[役立](../office-365-security/defender-for-office-365.md)ちます。  |
| **エンドポイント**  > **検索** | Microsoft Defender for Business (プレビュー) にオンボードされた 1 つ以上のデバイスを検索できます。 |
| **エンドポイント**  > **デバイス インベントリ** | Microsoft Defender for Business (プレビュー) にオンボードされた 1 つ以上のデバイスを検索できます。 |
| **エンドポイント**  > **脆弱性の管理** | ダッシュボード、推奨事項、修復アクティビティ、ソフトウェア インベントリ、および会社内の潜在的な弱点の一覧を提供します。 |
| **エンドポイント**  > **チュートリアル** | 脅威保護機能の動作の詳細については、チュートリアルとシミュレーションにアクセスできます。 <br/><br/>各チュートリアルの **シミュレーション ファイルを取得** する前に、[チュートリアルの読み取り] リンクを選択します。 一部のシミュレーションではOfficeを読むには、Microsoft Wordなどのアプリを使用する必要があります。 |
| **エンドポイント**  > **デバイス構成** | オペレーティング システム別および種類別にセキュリティ ポリシーを一覧表示します。 <br/><br/>セキュリティ ポリシーと設定の詳細については、「Microsoft Defender for Business (プレビュー)でポリシーを表示または編集する [」を参照してください](mdb-view-edit-policies.md)。 |
| **レポート** | 使用可能なセキュリティ レポートの一覧を表示します。 これらのレポートを使用すると、セキュリティの傾向を確認し、脅威の検出とアラートに関する詳細を表示し、会社の脆弱なデバイスの詳細を確認できます。 |
| **正常性** | サービスの正常性状態を表示し、今後の変更を計画できます。 <br/>- [**サービスの正常性]** を選択して、Microsoft 365に含まれるサービスの正常性状態を表示します。 <br/>- [ **メッセージ センター] を** 選択して、計画された変更と予想される変更について確認します。  |
| **ロール&アクセス許可** | セキュリティを管理する会社のユーザーにアクセス許可を割り当て、インシデントとレポートを Microsoft 365 Defenderできます。 また、デバイス グループをセットアップおよび管理して、会社のデバイスをオンボードし、脅威保護ポリシーを割り当てすることもできます。  |
| **設定** | ポータルと Microsoft Defender for Business (プレビュー) Microsoft 365 Defender設定を編集できます。 たとえば、オンボード (またはオフボード) と会社のデバイス (エンドポイントとも呼ばれます) を使用できます。 アラート抑制ルールなどのルールを定義し、特定のファイルまたはプロセスをブロックまたは許可するインジケーターを設定することもできます。  |
| **その他のリソース** | 他のポータル (Azure Active Directory など) に移動します。 他のポータルに移動する必要Microsoft 365 Defender、ユーザーのニーズを満たす必要がある場合は、このポータルに注意してください。 |

## <a name="complete-a-learning-module-about-incidents-and-response-actions"></a>インシデントと応答アクションに関する学習モジュールを完了する

インシデントと対応 [アクションの概要](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)については、学習モジュール「セキュリティの問題を検出して対応する」を参照してください。 インシデント キュー、アラート、および対応アクションについて説明します。 このコースは、Defender for Business (プレビュー) でインシデントの操作を開始するのに役立ちます。

> [!NOTE]
> ラーニング モジュール[(セキュリティ](/learn/modules/m365-detect-respond-security-issues-defender-endpoint/)の問題の検出と対応) は実際には Microsoft Defender for Endpoint 用ですが、基本的な概念と全体的なフローは、Defender for Business (プレビュー) に表示される内容と似ています。

## <a name="next-steps"></a>次の手順

Defender for Business (プレビュー) の概要が表示されたので、次のタスクを 1 つ以上試してください。

- [Microsoft Defender for Business でチュートリアルとシミュレーションを試す (プレビュー)](mdb-tutorials.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)

- [Microsoft Defender for Business でポリシーを表示または編集する (プレビュー)](mdb-view-edit-policies.md)