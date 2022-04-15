---
title: Microsoft 365 Defender ポータルにアクセスする
description: Microsoft 365 Defender ポータルの使用を開始する方法について説明します。 ポータルを移動し、現在のセキュリティ状態と推奨事項を表示する方法について説明します
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
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 4af2986a3c1c726e9bf963752d53fe6ef098c19e
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861468"
---
# <a name="visit-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルにアクセスする

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) は、Microsoft Defender for Businessを使用および管理するためのワンストップ ショップです。 開始に役立つウェルカム バナーと吹き出し、関連情報を表示するカード、さまざまな機能に簡単にアクセスできるナビゲーション バーが含まれています。 

:::image type="content" source="../../media/defender-business/mdb-portal-home.png" alt-text="Microsoft 365 Defender ポータル":::

 
>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="the-navigation-bar"></a>ナビゲーション バー

画面の左側にあるナビゲーション バーを使用して、インシデントにアクセスし、レポートを表示し、セキュリティ ポリシーを管理します。 次の表では、ナビゲーション バーに表示される項目について説明します。

| アイテム | 説明 |
|:---|:---|
| **ホーム** | Microsoft 365 Defenderのホーム ページに移動します。 ホーム ページには、検出されたアクティブな脅威を強調表示するカードと、会社のデータとデバイスのセキュリティ保護に役立つ推奨事項が含まれています。 <br/><br/>Defender for Business に含まれるおすすめは、セキュリティ チームの時間と労力を節約できます。 おすすめは業界のベスト プラクティスに基づいています。 推奨事項の詳細については、「セキュリティに関[する推奨事項 - 脅威と脆弱性の管理](../defender-endpoint/tvm-security-recommendation.md)」を参照してください。 |
| **インシデント** | 最近発生したインシデントの一覧に移動します。 アラートがトリガーされると、インシデントが作成されます。 インシデントには、複数のアラートを含めることができます。 インシデントは定期的に確認してください。 <br/><br/>インシデントの詳細については、「[Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)」を参照してください。|
| **アクション センター** | 完了したアクションや保留中のアクションなど、応答アクションの一覧に移動します。 <br/>- [ **履歴** ] タブを選択して、実行されたアクションを表示します。 一部のアクションは自動的に実行されます。他のユーザーは、承認された後に手動で実行されるか、完了します。 <br/>- **[保留中]** タブを選択して、続行するために承認が必要なアクションを表示します。 <br/><br/>アクション センターの詳細については、「アクション センター [で修復アクションを確認する」を参照してください](mdb-review-remediation-actions.md)。 |
| **脅威分析** | 現在の脅威のビューに移動し、脅威の状況を一目で確認できます。 脅威分析には、Microsoft セキュリティ研究者からのレポートと情報も含まれています。 <br/><br/>脅威分析の詳細については、「脅威 [分析を使用して新たな脅威を追跡して対応する](../defender-endpoint/threat-analytics.md)」を参照してください。 |
| **セキュア スコア** | 会社のセキュリティポジションの表現を提供し、それを改善するための提案を提供します。<br/><br/>セキュア スコアの詳細については、「 [Microsoft Secure Score for Devices](../defender-endpoint/tvm-microsoft-secure-score-devices.md)」を参照してください。 |
| **ラーニング ハブ** | サブスクリプションに含まれるラーニング パスを使用して、セキュリティ トレーニングやその他のリソースにアクセスできるようにします。 製品、スキル レベル、ロールなどによってフィルター処理できます。 ラーニング ハブを使用すると、セキュリティ チームが Defender for Business の機能&セキュリティ機能や、[Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)や[Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md)などの Microsoft 製品の機能を強化するのに役立ちます。  |
| **エンドポイント** > **検索** | Microsoft Defender for Businessにオンボードされた 1 つ以上のデバイスを検索できます。 |
| **エンドポイント** > **デバイス インベントリ** | Microsoft Defender for Businessにオンボードされた 1 つ以上のデバイスを検索できます。 |
| **エンドポイント** > **脆弱性の管理** | ダッシュボード、推奨事項、修復アクティビティ、ソフトウェア インベントリ、社内の潜在的な弱点の一覧を提供します。 |
| **エンドポイント** > **チュートリアル** | 脅威保護機能のしくみの詳細を学習するのに役立つチュートリアルとシミュレーションへのアクセスを提供します。 <br/><br/>各チュートリアルのシミュレーション ファイルを取得する前に、[ **チュートリアルの読み取り** ] リンクを選択します。 一部のシミュレーションでは、チュートリアルを読み取るために、Microsoft WordなどのOffice アプリが必要です。 |
| **エンドポイント** > **デバイスの構成** | オペレーティング システムと種類別にセキュリティ ポリシーを一覧表示します。 <br/><br/>セキュリティ ポリシーの詳細については、「[Microsoft Defender for Businessでポリシーを表示または編集](mdb-view-edit-policies.md)する」を参照してください。 |
| **レポート** | 使用可能なセキュリティ レポートを一覧表示します。 これらのレポートを使用すると、セキュリティの傾向を確認したり、脅威の検出とアラートに関する詳細を表示したり、会社の脆弱なデバイスの詳細を確認したりできます。 |
| **正常性** | サービスの正常性状態を表示し、今後の変更を計画できるようにします。 <br/>- **サービス正常性** を選択して、会社のサブスクリプションに含まれるMicrosoft 365 サービスの正常性状態を表示します。 <br/>- **メッセージ センター** を選択して、計画的な変更と予想される内容を確認します。  |
| **ロール&アクセス許可** | セキュリティを管理し、Microsoft 365 Defender ポータルでインシデントやレポートを表示する会社のユーザーにアクセス許可を割り当てることができます。 また、会社のデバイスをオンボードし、脅威保護ポリシーを割り当てるためにデバイス グループを設定および管理することもできます。  |
| **設定** | Microsoft 365 Defender ポータルとMicrosoft Defender for Businessの設定を編集できます。 たとえば、オンボード (またはオフボード) と会社のデバイス (エンドポイントとも呼ばれます) を使用できます。 アラート抑制ルールなどのルールを定義し、特定のファイルまたはプロセスをブロックまたは許可するインジケーターを設定することもできます。  |
| **その他のリソース** | Azure Active Directoryなど、他のポータルに移動します。 Microsoft 365 Defender ポータルは、他のポータルに移動しなくてもニーズを満たす必要があることに注意してください。 |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessでセットアップ ウィザードを使用する](mdb-use-wizard.md)
- [セットアップと構成プロセスを確認する](mdb-setup-configuration.md)