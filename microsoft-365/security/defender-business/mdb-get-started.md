---
title: Microsoft 365 Defender ポータルにアクセスする
description: Defender for Business のセキュリティ センターは、Microsoft 365 Defender ポータルです。 ポータルを移動する方法について説明し、次の手順を確認します。
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
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 1e518bdb3436405aea9e131a0cf08b0754cebb95
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773199"
---
# <a name="visit-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルにアクセスする

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) は、Microsoft Defender for Businessを使用および管理するためのワンストップ ショップです。 これには、作業を開始するのに役立つ吹き出し、関連情報を表示するカード、さまざまな機能に簡単にアクセスできるナビゲーション バーが含まれています。

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Microsoft 365 Defender ポータル":::

## <a name="the-navigation-bar"></a>ナビゲーション バー

画面の左側にあるナビゲーション バーを使用して、インシデントにアクセスし、レポートを表示し、セキュリティ ポリシーを管理します。 次の表では、ナビゲーション バーに表示される項目について説明します。

| アイテム | 説明 |
|:---|:---|
| **ホーム** | Microsoft 365 Defender ポータルでホーム ページに移動します。 ホーム ページには、検出されたアクティブな脅威と、会社のデータとデバイスのセキュリティ保護に役立つ推奨事項が強調表示されています。 <br/><br/>Defender for Business には、セキュリティ チームの時間と労力を節約するための推奨事項が含まれています。 推奨事項は、業界のベスト プラクティスに基づいています。 詳細については、「[セキュリティに関する推奨事項 - 脅威と脆弱性の管理](../defender-endpoint/tvm-security-recommendation.md)」を参照してください。 |
| **インシデント** | 最近発生したインシデントの一覧に移動します。 アラートがトリガーされると、インシデントが作成されます。 インシデントには、複数のアラートを含めることができます。 インシデントは定期的に確認してください。 <br/><br/>詳細については、「 [Defender for Business でのインシデントの表示と管理」を](mdb-view-manage-incidents.md)参照してください。|
| **申請** > &アクション **アクション センター** | 完了したアクションや保留中のアクションなど、応答アクションの一覧に移動します。<ul><li>[ **履歴** ] タブを選択して、実行されたアクションを表示します。 一部のアクションは自動的に実行されます。他のユーザーは、承認された後に手動で実行されるか、完了します。</li><li>[ **保留中]** タブを選択して、続行するために承認が必要なアクションを表示します。</li></ul><br/><br/>詳細については、「 [アクション センターで修復アクションを確認する」を参照してください](mdb-review-remediation-actions.md)。 |
| **申請** > &アクション **提出** | 統合申請ポータルに移動し、ファイルを Microsoft に送信して分析を行うことができます。 詳細については、「[Microsoft Defender for Endpointでファイルを送信する](../defender-endpoint/admin-submissions-mde.md) (このプロセスは Defender for Business に似ています)」を参照してください。 |
| **脅威の分析** | 現在の脅威のビューに移動し、脅威の状況を一目で確認できます。 脅威分析には、Microsoft セキュリティ研究者からのレポートと情報も含まれています。 <br/><br/>詳細については、「 [脅威分析を使用して、新たな脅威を追跡して対応する](../defender-endpoint/threat-analytics.md)」を参照してください。 |
| **セキュア スコア** | 会社のセキュリティ上の立場を表し、それを改善するための提案を提供します。<br/><br/>詳細については、「 [デバイスの Microsoft セキュリティ スコア](../defender-endpoint/tvm-microsoft-secure-score-devices.md)」を参照してください。 |
| **ラーニング ハブ** | サブスクリプションに含まれるラーニング パスを使用して、セキュリティ トレーニングやその他のリソースにアクセスできるようにします。 製品、スキル レベル、ロールなどによってフィルター処理できます。 ラーニング ハブを使用すると、セキュリティ チームが Defender for Business のセキュリティ機能や、[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)や[Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md)などの Microsoft 製品のセキュリティ機能を強化するのに役立ちます。  |
| **試験** | 試用版サブスクリプションに追加することで、追加のセキュリティ機能とコンプライアンス機能を試してください。 |
| **エンドポイント** > **デバイス インベントリ** | Defender for Business にオンボードされた 1 つ以上のデバイスを検索できます。 |
| **エンドポイント** > **脆弱性の管理** | ダッシュボード、推奨事項、修復アクティビティ、ソフトウェア インベントリ、社内の潜在的な弱点の一覧を提供します。 |
| **エンドポイント** > **チュートリアル** | 脅威保護機能のしくみの詳細を学習するのに役立つチュートリアルとシミュレーションへのアクセスを提供します。 <br/><br/>各チュートリアルのシミュレーション ファイルを取得する前に、[ **チュートリアルの読み取り** ] リンクを選択します。 一部のシミュレーションでは、チュートリアルを読むには、Microsoft Word などの Office アプリが必要です。 |
| **エンドポイント** > **構成管理** > **デバイスの構成** | オペレーティング システムと種類別にセキュリティ ポリシーを一覧表示します。 <br/><br/>セキュリティ ポリシーの詳細については、「 [Defender for Business のポリシーを表示または編集](mdb-view-edit-policies.md)する」を参照してください。 |
| **エンドポイント** > **構成管理** > **デバイス管理レポート** | Defender for Business にオンボードされているデバイスと、オペレーティング システムのバージョン、センサーの正常性状態、および最後に更新された日時を一覧表示します。 |
| **レポート** | 使用可能なセキュリティ レポートを一覧表示します。 これらのレポートを使用すると、セキュリティの傾向を確認したり、脅威の検出とアラートに関する詳細を表示したり、会社の脆弱なデバイスの詳細を確認したりできます。 |
| **正常性** | サービスの正常性状態を表示し、今後の変更を計画できるようにします。 <ul><li>**サービス正常性** を選択すると、会社のサブスクリプションに含まれる Microsoft 365 サービスの正常性状態が表示されます。</li><li>**[メッセージ センター**] を選択して、計画的な変更と想定される内容について確認します。</li></ul>  |
| **アクセス許可** | セキュリティを管理する会社のユーザーにアクセス許可を割り当て、Microsoft 365 Defender ポータルでインシデントとレポートを表示できるようにします。 また、会社のデバイスをオンボードし、脅威保護ポリシーを割り当てるためにデバイス グループを設定および管理することもできます。  |
| **設定** | Microsoft 365 Defender ポータルと Defender for Business の設定を編集できます。 たとえば、会社のデバイス (エンドポイントとも呼ばれます) をオンボード (またはオフボード) できます。 アラート抑制ルールなどのルールを定義し、特定のファイルまたはプロセスをブロックまたは許可するインジケーターを設定することもできます。  |
| **その他のリソース** | Azure Active Directory などの他のポータルに移動します。 ただし、Microsoft 365 Defender ポータルは、他のポータルに移動しなくてもニーズを満たす必要があることに注意してください。 |

## <a name="next-steps"></a>次の手順

- [Defender for Business でセットアップ ウィザードを使用する](mdb-use-wizard.md)
- [全体的なセットアップと構成プロセスを確認する](mdb-setup-configuration.md)