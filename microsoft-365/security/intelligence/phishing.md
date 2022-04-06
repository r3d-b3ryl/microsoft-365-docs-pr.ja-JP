---
title: フィッシング攻撃から保護する方法
ms.reviewer: ''
description: フィッシングの動作、マルウェアの配信によるデバイスの動作、および自分を保護するために実行できる操作について学ぶ
keywords: セキュリティ, マルウェア, フィッシング, 情報, 詐欺, ソーシャル エンジニアリング, 餌, ルアー, 保護, 傾向, 標的型攻撃
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
ms.openlocfilehash: 39b998b69b62a8c927ff26c1325d8a88812e0be6
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683488"
---
# <a name="how-to-protect-against-phishing-attacks"></a>フィッシング攻撃から保護する方法

フィッシング攻撃は、電子メール、Web サイト、テキスト メッセージ、または他の形式の電子通信を介して機密情報を盗もうとします。 正当な企業や個人からの公式なコミュニケーションのように見える。

サイバー犯罪者は、多くの場合、ユーザー名、パスワード、クレジット カードの詳細、銀行口座情報、または他の資格情報を盗もうとします。 盗まれた情報は、ハッキング、ID 盗難、銀行口座やクレジット カードから直接お金を盗むなどの悪意のある目的で使用されます。 この情報は、サイバー犯罪の地下市場でも販売できます。

ソーシャル エンジニアリング攻撃は、意思決定におけるユーザーの可能な経過を利用するように設計されています。 電子メールや不明な Web サイト、または電話を通じて、機密情報や個人情報を提供し、決して注意してください。 フィッシングメールは正当に表示するように設計されています。

## <a name="learn-the-signs-of-a-phishing-scam"></a>フィッシング詐欺の兆候を確認する

最善の保護は、意識と教育です。 電子メールが認識されたソースから送信された場合でも、迷惑メールの添付ファイルやリンクを開かれません。 メールが予期しない場合は、添付ファイルを開いて URL を確認してください。

企業は、個人情報や財務情報を要求するコミュニケーションに対して従業員を教育し、訓練する必要があります。 また、従業員に対して、直ちに会社のセキュリティ運用チームに脅威を報告するよう指示する必要があります。

フィッシング詐欺の兆候を次に示します。

* 電子メールで提供されるリンクまたは URL は、正しい場所を指していないか、メールの送信者と関連付けされていないサードパーティ のサイトを指しています。 たとえば、指定された URL の下の画像では、取得先の URL と一致しません。

    ![URL にカーソルを合わせる例を示します。](../../media/security-intelligence-images/url-hover.png)

* 社会保障番号 **や銀行情報、財務** 情報などの個人情報の要求があります。 公式の通信では、通常、電子メールの形式で個人情報を要求する必要があります。

* **電子メール アドレス内のアイテムは、** 正当な電子メール アドレスと十分に似ていますが、数字または変更された文字が追加された場合に変更されます。

* メッセージは予期 **せず、非送信請求です**。 エンティティまたはめったに扱う人から突然メールを受け取った場合は、このメールの疑いを考慮してください。

* メッセージまたは添付ファイルから、マクロの有効化、セキュリティ設定の調整、またはアプリケーション **のインストールを求めるメッセージが表示されます**。 通常のメールでは、これを行う必要は表示されます。

* メッセージにはエラーが **含まれています**。 正当な企業メッセージは、誤字や文法上のエラーが発生したり、間違った情報が含まれている可能性が低い。

* 送信者 **アドレスがメッセージ自体の署名** と一致しません。 たとえば、電子メールは Contoso Corp の Mary からのメールと見なされますが、送信者のアドレスは john<span></span>@example.com。

* [宛先 **] フィールドには** 複数の受信者がいて、ランダムなアドレスとして表示されます。 企業メッセージは通常、個々の受信者に直接送信されます。

* メッセージ自体の案内応答 **は、個人的に対処しません**。 別のユーザーに誤って対処するメッセージとは別に、自分の名前を誤用したり、メール アドレスから直接名前を引き出したりする案内応答は、悪意のあるものになる傾向があります。

* Web サイトは見慣れたように見えますが、不整合や正 **しくないものがあります**。 警告記号には、古いロゴ、入力ミス、または正当なサインイン Web サイトから求めされない追加情報の提供をユーザーに求めるメッセージが含まれます。

* 開くページは **、ライブ ページ** ではなく、使い慣れたサイトのように設計された画像です。 資格情報を要求するポップアップが表示される場合があります。

疑わしい場合は、既知のチャネルからビジネスに問い合わせ、疑わしいメールが実際に正当なものか確認してください。

## <a name="software-solutions-for-organizations"></a>組織向けソフトウェア ソリューション

* [Microsoft Edge](/microsoft-edge/deploy/index)[およびWindows Defender Application Guard](/windows/security/microsoft-defender-application-guard/md-app-guard-overview.md)は、Microsoft の業界をリードする Hyper-V 仮想化テクノロジを使用して、標的型攻撃の増大する脅威からの保護を提供します。 参照された Web サイトが信頼されていないと判断された場合、Hyper-V コンテナーは、そのデバイスをネットワークの残りの部分から分離するため、エンタープライズ データへのアクセスを防止します。

* [Microsoft Exchange Online保護 (EOP)](https://products.office.com/exchange/exchange-email-security-spam-protection) は、緊急時および緊急時のメールへのアクセスを維持しながら、エンタープライズ クラスの信頼性とスパムやマルウェアに対する保護を提供します。  EOP は、さまざまなレイヤーのフィルター処理を使用して、バルク メール制御や国際スパムなどのスパム フィルター処理のさまざまなコントロールを提供し、保護サービスをさらに強化できます。

* [Microsoft Defender を使用Office 365](https://products.office.com/exchange/online-email-threat-protection?ocid=cx-blog-mmpc)メール、ファイル、およびオンライン ストレージをマルウェアから保護します。 この機能は、Microsoft Teams、Word、Excel、PowerPoint、Visio、SharePoint オンライン、およびOneDrive for Business。 安全でない添付ファイルから保護し、悪意のあるリンクに対する保護を拡大することで、Exchange Online Protection のセキュリティ機能を補完し、ゼロデイ保護を強化します。

## <a name="what-to-do-if-youve-been-a-victim-of-a-phishing-scam"></a>フィッシング詐欺の被害に見合った場合の操作

フィッシング攻撃の被害を受けたと感じた場合は、次の手順を行います。

1. 仕事用コンピューターを使用している場合は、IT 管理者に問い合わせ
2. アカウントに関連付けられているすべてのパスワードを直ちに変更する
3. 詐欺行為を銀行やクレジット カード会社に報告する

### <a name="reporting-spam"></a>スパムの報告

- **Outlook.com**: 個人情報を求める不審な電子メール メッセージを受信する場合は、受信トレイのメッセージの横にあるチェック ボックスOutlookします。 [迷惑メール] の横にある **矢印を選択** し、[フィッシング] **を選択します**。

- **Microsoft Office Outlook**: 疑わしいメッセージの中で、リボンから **[** メッセージの報告] を選択し、[フィッシング] **を選択します**。

- **Microsoft 365**: 迷惑メールまたはフィッシング サンプル [](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)を分析Microsoft 365 Defender送信するには、アプリの [申請] ポータルを使用します。 詳細については、「[メッセージとファイルを Microsoft に報告する](/microsoft-365/security/office-365-security/report-junk-email-messages-to-microsoft)」を参照してください。

- **フィッシング対策作業グループ: phishing-report@us-cert.gov**。 グループは、フィッシング詐欺やハッカーと戦うために送信されたメールから生成されたレポートを使用します。 ISP、セキュリティ ベンダー、金融機関、法執行機関が関与しています。

### <a name="if-youre-on-a-suspicious-website"></a>疑わしい Web サイトにアクセスしている場合

- **Microsoft Edge**: 不審なサイトにアクセスしている間に、[その他] **(...) iconHelp** >  と **feedbackReport** >  **Unsafe サイトを選択します**。 表示される Web ページの指示に従って、Web サイトを報告します。

- **Internet Explorer**: 疑わしいサイトにアクセスしている間は、歯車アイコンを選択し、[安全] をポイントし、[安全でない Web サイトの報告] **を選択します**。 表示される Web ページの指示に従って、Web サイトを報告します。

## <a name="more-information-about-phishing-attacks"></a>フィッシング攻撃の詳細

- [フィッシングから身を守る](https://support.microsoft.com/help/4033787/windows-protect-yourself-from-phishing)
- [フィッシングの傾向](phishing-trends.md)
