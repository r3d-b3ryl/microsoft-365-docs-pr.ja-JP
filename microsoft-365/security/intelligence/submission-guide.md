---
title: Microsoft による分析用のファイルの送信
description: マルウェア分析のためにファイルを Microsoft に送信する方法、申請を追跡する方法、および紛争の検出について説明します。
ms.reviewer: ''
keywords: セキュリティ、サンプル提出ヘルプ、マルウェア ファイル、ウイルス ファイル、トロイの木馬ファイル、送信、Microsoft への送信、サンプルの提出、ウイルス、トロイの木馬、ワーム、検出されない、検出されない、電子メール microsoft、電子メール マルウェア、これはマルウェアだと思います、ウイルスを送信できるウイルス、これはウイルス、MSE、検出なし、署名なし、検出、疑わしいファイル、です。 MMPC、Microsoft マルウェア プロテクション センター、研究者、アナリスト、WDSI、セキュリティ インテリジェンス
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 78f1e00555d36880f24f05d213f42725f4ac0133
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680317"
---
# <a name="submit-files-for-analysis"></a>分析用にファイルを送信する

マルウェアの疑いのあるファイルや、誤って検出されたファイルがある場合は、分析のために提出してください。 このページには、分析用にファイルを提出する際の一般的な質問に対する回答があります。

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>Microsoft にマルウェア ファイルを送信する方法

サンプル提出ポータルを通じて、マルウェアまたは誤って検出されたファイルと思うファイルを送信 [できます](https://www.microsoft.com/en-us/wdsi/filesubmission)。

多くのソースから多数のサンプルを受け取っています。 分析の優先順位は、ファイル検出の数と送信の種類です。 使用していた製品と、ファイルを見つけたときに何をしていたかについての詳細情報を提供することで、迅速な分析を完了できます。

サインインすると、申請を追跡できます。

## <a name="can-i-send-a-sample-by-email"></a>サンプルを電子メールで送信できますか?

いいえ、提出はサンプル提出ポータルを通じて [のみ受け入れ可能です](https://www.microsoft.com/en-us/wdsi/filesubmission)。

## <a name="can-i-submit-a-sample-without-signing-in"></a>サインインせずにサンプルを送信できますか?

いいえ。 エンタープライズ顧客の場合は、申請の優先順位を適切に設定するためにサインインする必要があります。 現在、ウイルスの発生やセキュリティ関連のインシデントが発生している場合は、指定された Microsoft サポート担当者に連絡するか、 [Microsoft サポート](https://support.microsoft.com/) に直接問い合わせてください。

## <a name="what-is-the-software-assurance-id-said"></a>ソフトウェア アシュアランス ID (SAID) とは何ですか?

ソフトウェア [アシュアランス ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) は、エンタープライズのお客様がサポート資格を追跡するために使用します。 申請ポータルは SAID 情報を受け入れて保持し、有効な SAID を持つ顧客が優先度の高い申請を行うのを許可します。

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>プログラムの検出に異議を唱えてください。

[問題のファイルを](https://www.microsoft.com/en-us/wdsi/filesubmission) ソフトウェア開発者として提出します。 提出が最終的な決定を得るまで待ちます。

申請の決定に満足できない場合は、申請結果に提供された開発者連絡先フォームを使用して Microsoft に連絡してください。 お客様が提供した情報を使用して、必要に応じてさらに調査を行います。

Microsoft がマルウェアと望ましくないソフトウェアを識別する方法について、すべてのソフトウェア ベンダーと開発者 [に読んでお勧めしています](criteria.md)。

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>過去のサンプル申請を追跡または表示する方法

提出履歴ページを使用して、申請 [を追跡できます](https://www.microsoft.com/en-us/wdsi/submissionhistory)。

## <a name="what-does-the-submission-status-mean"></a>申請の状態は何を意味しますか?

各申請は、次のいずれかの状態の種類に表示されます。

* 送信済み - ファイルが受信されました

* 進行中- アナリストがファイルのチェックを開始しました

* [終了] - アナリストが最終的な決定を行いました

提出履歴ページで、提出したファイルの状態 [を確認できます](https://www.microsoft.com/en-us/wdsi/submissionhistory)。

## <a name="how-does-microsoft-prioritize-submissions"></a>Microsoft が申請に優先順位を付ける方法

申請の処理には、専用のアナリスト リソースが必要です。 定期的に多数の提出を受け取るので、優先度に基づいて処理します。 次の要因は、申請の優先順位付け方法に影響します。

* 多数のコンピューターに影響を与える可能性のある一般的なファイルが優先されます。

* 認証された顧客、特に有効なソフトウェア アシュアランス [ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) を持つエンタープライズのお客様が優先されます。

* SAID 所有者による優先度の高いフラグが付いた申請は、直ちに注意を払います。

アナリストがケースの処理を開始する前に、お客様の提出が直ちにシステムによってスキャンされ、最新の判断が下されます。 同じファイルがアナリストによって既に処理されている可能性があります。 決定の更新を確認するには、申請の詳細ページで [再スキャン] を選択します。
