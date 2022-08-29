---
title: Power Automate コネクタを使用して Bookings ワークフローを構築する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
description: Power Automate Bookings Connectors を使用して、予定トリガーを使用してカスタム ワークフローを作成します。
ms.openlocfilehash: ca37f33d77d83fd13f7719edb345c7150d8226c0
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360732"
---
# <a name="use-power-automate-connectors-to-build-bookings-workflows"></a>Power Automate コネクタを使用して Bookings ワークフローを構築する

Microsoft Bookings コネクタは、Power Platform が提供するその他の機能を使用して Booking の予定を拡張するために構築されています。 ビジネス顧客の予定のカスタム ワークフローを構築したい場合 (たとえば、顧客が Zoom 会議と予定を予約できるようにする、Stripe を使用した支払い方法の統合、CRM システムへの顧客データのアップロード、ウェルカム メールの送信など) は、Bookings Connector が Bookings ソリューションです。

## <a name="before-you-begin"></a>はじめに

Bookings Connector を使用する顧客は、Bookings ライセンスを持っている必要があります。 Microsoft Bookingsライセンスとサブスクリプションの詳細については、「[よく寄せられる質問Microsoft Bookings](bookings-faq.yml#is-bookings-available-for-my-subscription-)参照してください。

Microsoft Bookingsでは、Azure Active Directory (AAD) 認証が使用されます。 有効な Microsoft 365 アカウントを使用すると、Bookings Connector の使用が確実に認証されます。 予定ベースのフローを作成するには、サインインしている必要があります。

Bookings の予定をトリガーとして使用するカスタム フローを作成するには、Bookings ビジネス SMTP アドレスを指定する必要があります。

![SMTP アドレスの画像。](media/bookings-teams-smtp.png)

## <a name="get-started-with-connectors"></a>コネクタの概要

Microsoft Bookings コネクタを使用して構築できる一般的なフローの一部を次に示します。

### <a name="integration-with-stripe"></a>Stripe との統合

Stripe を使用すると、個人や企業はインターネット経由で支払いを受け入れます。 顧客、注文、請求書などを追跡できます。 詳細については、「ストライプ |」を参照してください。 [Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_stripe/stripe/)。

### <a name="integration-with-zoom"></a>Zoom との統合

Zoom Meetings コネクタは、Zoom 会議操作を自動化するのに役立ちます。 詳細については、「 [Zoom Meetings (Independent Publisher) |Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_zoommeetingsip/zoom-meetings-independent-publisher/)。

### <a name="integration-with-dynamic-365"></a>Dynamic 365 との統合

Dynamics 365 Sales Insights は、パーソナライズされたエンゲージメントと積極的な意思決定を促進し、リレーションシップの構築に役立つ人工知能 (AI) 主導の分析情報を利用して、売上を増加させます。 詳細については、「 [Dynamics 365 Sales Insights |」を参照してください。Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/details/shared_assistantstudio/dynamics-365-sales-insights/)。

使用可能なすべての Bookings コネクタについては、「 [サポートされているコネクタ |」を参照してください。Microsoft Power Automate](https://powerautomate.microsoft.com/connectors/)。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

- **予定トリガーを使用してフローを作成できるのは管理者だけです。** Bookings 管理者のみが予定トリガーを作成できます。 管理者 (チーム メンバー、スケジューラ、ビューアー、ゲスト) ではないユーザーの場合は、管理者にフローの作成を依頼する必要があります。 または、管理者アクセスを要求することもできます。

- **Bookings メールボックスごとに作成できるフローは 5 つだけです。** これは Bookings メールボックス レベルの制限であり、管理者ごとの制限ではありません。 予定トリガーに対して複数のアクションが必要な場合は、[アクションの追加] ボタンを使用して既存のフローのいずれかに **アクションを追加** できます。 サポートについては、他の Booking 管理者にお問い合わせください。

- **一部の Bookings パラメーターは設定されません。** 1:1 の予約のキャンセル理由とカスタム ノートは設定されません。 この修正は間もなくロールアウトされます。

- **フローの作成中のエラー コードは完全には表示されません。** フローの作成時に発生する可能性のあるエラーは、フロー ポータルには表示されません。 この修正プログラムは進行中であり、次のリリースで使用できるようになります。

## <a name="common-errors-and-remedies"></a>一般的なエラーと対処法

フローの作成時の HTTP エラー コード:

- '401': 接続で認証関連の問題を確認します。
- '403': 予約管理者のみが予定フローを作成できます。 上記の「既知の問題と制限事項」の最初の問題を参照してください。
- '403': 通知 URL ドメインは許可リストの一部ではありません。
- '429': 予想される数を超える予定フローがビジネス用に作成されました。 上記の「既知の問題と制限事項」の Bookings メールボックスあたりの 5 つのフローの制限を参照してください。
- '500': これは内部サーバー エラーです。 このエラーをサポート エンジニアに報告し、フロー作成応答にエラーの詳細を含めます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**予定トリガー ベースのフローを作成するための SMTP アドレスを取得操作方法。**

予定トリガーベースのフローを作成するには、作成者が Bookings ビジネスの SMTP アドレスを取得する必要があります。 これは、グラフ呼び出しを行うために使用されるのと同じ SMTP アドレスです。 これは、Bookings ページ URL の一部でもあります。

**予定トリガーの応答から顧客データを取得するにはどうすればよいですか?**

1:1 の予約では、CustomerName、CustomerEmail などの最上位フィールドを使用できます。 グループ予約の場合、顧客配列は、power automate ループ コンポーネントを使用して displayName、customers email、customers displayName などのフィールドを使用できます。

**StaffMembers が配列である理由**

複数のスタッフ メンバーをホストとして割り当てることができます。 サービスにホストとして割り当てられているスタッフ メンバーが 1 つだけの場合、スタッフの詳細はスタッフ メンバー配列に表示されます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft Power Automate コネクタ](https://make.preview.powerautomate.com/connectors/shared_microsoftbookings/microsoft-bookings/)\
[Microsoft Bookings (プレビュー) リファレンス](/connectors/microsoftbookings/) (記事)