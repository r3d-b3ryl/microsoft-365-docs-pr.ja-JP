---
title: Microsoft による分析のためにファイルを送信する
description: マルウェア分析、提出物の追跡方法、およびクレーム検出のために Microsoft にファイルを送信する方法について説明します。
ms.reviewer: ''
keywords: セキュリティ、サンプル送信ヘルプ、マルウェア ファイル、ウイルス ファイル、トロイの木馬ファイル、送信、Microsoft への送信、サンプル、ウイルス、トロイの木馬、みず、検出されない、検出されない、電子メール Microsoft、電子メール マルウェア、これはマルウェアだと思う、ウイルスだと思う、ウイルスを送信できる場所はウイルス、MSE、検出しない、署名なし、検出なし、疑わしいファイル MMPC、Microsoft マルウェア プロテクション センター、研究者、アナリスト、WDSI、セキュリティ インテリジェンス
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
ms.openlocfilehash: df2ab2b2019bb76af49f00d2751cdc76848705d1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663602"
---
# <a name="submit-files-for-analysis"></a>分析のためにファイルを送信する

マルウェアである可能性がある、または誤って検出されている可能性があるファイルがある場合は、分析のためにファイルを Microsoft に送信できます。 このページでは、分析用のファイルの送信に関するいくつかの一般的な質問に対する回答を示します。

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>マルウェア ファイルを Microsoft に送信操作方法?

[サンプル送信ポータル](https://www.microsoft.com/wdsi/filesubmission)を使用して、マルウェアまたは誤って検出されたファイルと思われるファイルを送信できます。

多くのソースから多数のサンプルを受け取ります。 分析は、ファイル検出の数と提出の種類によって優先順位が付けられます。 使用していた製品と、ファイルを見つけたときに実行していた内容に関する詳細情報を提供することで、簡単な分析を完了するのに役立ちます。

サインインすると、提出物を追跡できるようになります。

## <a name="can-i-send-a-sample-by-email"></a>サンプルをメールで送信できますか?

いいえ。提出は [サンプル送信ポータル](https://www.microsoft.com/wdsi/filesubmission)を通じてのみ受け付けられます。

## <a name="can-i-submit-a-sample-without-signing-in"></a>サインインせずにサンプルを送信できますか?

いいえ。 企業のお客様の場合は、提出の優先順位を適切に設定できるようにサインインする必要があります。 現在、ウイルスの発生またはセキュリティ関連のインシデントが発生している場合は、指定された Microsoft サポート 担当者に問い合わせるか[、Microsoft サポート](https://support.microsoft.com/)にお問い合わせください。

## <a name="what-is-the-software-assurance-id-said"></a>ソフトウェア アシュアランス ID (SAID) とは何ですか?

[ソフトウェア アシュアランス ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) は、エンタープライズのお客様がサポート資格を追跡するための ID です。 申請ポータルは SAID 情報を受け入れて保持し、有効な SAID を持つ顧客が優先度の高い提出を行えるようにします。

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>操作方法プログラムの検出に異議がありますか?

問題[のファイルを](https://www.microsoft.com/wdsi/filesubmission)ソフトウェア開発者として送信します。 提出が最終的な決定になるまで待ちます。

提出の決定に満足できない場合は、提出結果と共に提供される開発者の連絡先フォームを使用して Microsoft に連絡してください。 必要に応じて、お客様から提供された情報を使用してさらに調査します。

Microsoft が [マルウェアや望ましくない](criteria.md)ソフトウェアを識別する方法については、すべてのソフトウェア ベンダーと開発者に読み取ることをお勧めします。

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>過去のサンプル提出を追跡または表示操作方法?

提出履歴ページを使用して [、提出を](https://www.microsoft.com/wdsi/submissionhistory)追跡できます。

## <a name="what-does-the-submission-status-mean"></a>申請の状態は何を意味しますか?

各申請は、次のいずれかの状態の種類で表示されます。

* 送信済み - ファイルが受信されました

* 進行中 - アナリストがファイルのチェックを開始しました

* 終了 — アナリストによって最終的な決定が行われた

送信 [履歴ページ](https://www.microsoft.com/wdsi/submissionhistory)で、送信したファイルの状態を確認できます。

## <a name="how-does-microsoft-prioritize-submissions"></a>Microsoft が提出に優先順位を付ける方法

送信の処理には、専用のアナリスト リソースが必要です。 定期的に多数の提出を受け取るため、優先順位に基づいて処理します。 次の要因は、提出の優先順位を付ける方法に影響します。

* 多数のコンピューターに影響を与える可能性のある一般的なファイルが優先されます。

* 認証された顧客、特に有効な [ソフトウェア アシュアランス ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) を持つ企業のお客様が優先されます。

* SAID 所有者によって優先度が高いフラグが付けられた提出には、直ちに注意が払われます。

アナリストがケースの処理を開始する前に、お客様の提出が直ちにシステムによってスキャンされ、最新の判断が下されます。 同じファイルがアナリストによって既に処理されている可能性があることに注意してください。 決定の更新を確認するには、申請の詳細ページで再スキャンを選択します。
