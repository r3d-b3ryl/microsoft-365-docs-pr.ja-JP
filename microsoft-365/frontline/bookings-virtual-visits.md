---
title: Microsoft Teams と Bookings アプリを使用した仮想予定
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
ms.reviewer: ''
description: Teams の Bookings アプリを使用して仮想予定をスケジュール、管理、実行する方法について説明します。
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: ef4ca09cac8cc411e6b9b33b32b27c01265ddccf
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994996"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams と Bookings アプリを使用した仮想予定

## <a name="overview"></a>概要

Microsoft Teams の [Bookings アプリ](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)は、組織がスタッフと出席者の仮想予定をスケジュールおよび管理するための簡単な方法を提供します。 これを使用して、医療訪問、財務コンサルテーション、面接、顧客サポート、仮想試着と相談、教育オフィスの時間などの予定をスケジュールします。

Bookings アプリを使用すると、どの組織でもスケジュールに関する複雑なニーズを簡単に満たすことができます。 スケジュール管理者は、複数の部門やスタッフの予定表を管理できるだけでなく、1 つの操作環境で社内外の出席者とコミュニケーションをとることができます。

仮想予定は、強力なビデオ会議機能を提供する Microsoft Teams 会議を通して開催されます。 たとえば、医師は画面を共有して、患者と検査結果を確認できます。 銀行顧問の場合、ドキュメントに電子署名を要求して、取引をリモートで成立させることができます。

各仮想予定には、メールで出席者に送信される Teams 会議リンクが含まれています。このリンクで、Web ブラウザーから、または任意のデバイス上の Teams から簡単に会議に参加できます。 自動メール リマインダーは、ノーショーを減らし、顧客とクライアントのエンゲージメントを強化するのに役立ちます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Bookings を使用すると、業界に合わせてカスタマイズされたエクスペリエンスを得ることができます。 組織内で使用する方法の例のいくつかを次に示します。

|業界 | 例 |
|---------|---------|
|金融サービス    |  リモート販売とサービスの仮想予定<br/>効率と利便性を高めて顧客にサービスを提供するために、予定をスケジュールし、管理します。銀行のリレーションシップ マネージャー、財務アドバイザー、損害査定人など、さまざまなユーザーに役立ちます。  |
|小売   | 仮想試着と相談 <br/>営業担当者、製品エキスパート、および設計コンサルタントの予定をスケジュールおよび管理して、顧客の仮想試着や相談を行います。   |
|医療   |  患者ケアの仮想予定 <br/>ケア チームのメンバーが患者や他の医療従事者と会って医療について話し合うために、予定をスケジュールして管理します。   |

この記事では、Teams の Bookings アプリを使用して仮想予定をスケジュール、管理、実行する方法の概要を説明します。

## <a name="before-you-get-started"></a>使用を開始する前に

管理者の場合、「[Teams で Bookings アプリを管理する](/microsoftteams/bookings-app-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)」を参照してください。この記事では、Teams で Bookings アプリを使用するための前提条件、組織内で Bookings へのアクセスを制御する方法、推奨ポリシーと管理者設定について説明しています。

Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけであることに注意してください。 仮想予定の実施または参加をするスタッフがアプリを入手する必要はありません。 Teams または Outlook 予定表から、または予約確認メールの会議リンクを使用して、予定に参加できます。

## <a name="set-up-a-new-booking-calendar"></a>新しい予約予定表を設定する

### <a name="create-the-booking-calendar"></a>予約予定表を作成する

Teams で、**[Bookings]** > **[開始]** の順に移動し、**[新しい予約予定表]** を選択します。 フォームに入力し、必ず組織に関連する業種を選択します。

:::image type="content" source="media/bookings-virtual-visits-new-booking-calendar.png" alt-text="業種を示す新しい予約予定表画面のスクリーンショット":::

大規模な組織の場合、出席者が組織全体ではなく特定の部署から予約メールを受け取るようにするには、複数の予約予定表を作成することを検討します。
詳細については、「[Bookings 予定表を作成する](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)」を参照してください。

> [!NOTE]
> Bookings アプリを使用するのが初めてではない場合や、既存の予約予定表で作業する場合は、Bookings で組織名の隣にあるドロップダウン矢印を選択し、**[既存の予約予定表]** を選択します。 ここから、目的の予定表を検索できます。

### <a name="add-staff"></a>スタッフを追加する

予約予定表で、[**その他のオプション** (...)] > **[設定]** に移動し、**[スタッフ]** を選択します。 スタッフ メンバーを追加し、追加する各ユーザーにロールを割り当てます。 予約予定表には、最大 100 人のスタッフ メンバーを追加できます。

Bookings アプリは Outlook と統合します。 スタッフを追加すると、予定表の空き時間を表示し、予約のスケジュールを設定できるようになります。 詳細については、「[スタッフを追加して予約予定表を表示する](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)」を参照してください。  

### <a name="create-appointment-types"></a>予定の種類を作成する

組織が提供するサービスを示し、予約エクスペリエンスをカスタマイズするため、特定の予定の種類を作成します。 これを行うと、スケジュール管理者はその予定の種類を使用して予定をスケジュールできます。

予約予定表で、[**その他のオプション** (...)] > **[設定]** の順に移動し、**[予定の種類]**]を選択して、**[予定の種類の追加]** を選択します。 名前&mdash;アカウント開設、処方箋の更新、ローンの相談、納税準備など&mdash;、およびその他の必要な情報や設定を入力します。

追加する情報は、この種類の予定が予約されるたびに出席者に送信される確認メールに含まれます。 メール リマインダーやその他のオプション (出席者が Teams をダウンロードしなくても[デスクトップ ブラウザーまたはモバイル ブラウザーから参加](browser-join.md)できるかどうかなど) を設定できます。

Bookings 管理者の場合、この種類の予定が予約されるたびに出席者が入力するためのフォームを最大 4 つリンクできます。 たとえば、出席者が予定に参加する前に登録フォームに入力するように求めることがあるかもしれません。 フォームをリンクするには、**[フォームのリンク]** を選択します。 フォームの URL を入力し、**[リンク]** を選択します。 (フォームを初めてリンクする場合、フォームを保存する Microsoft 365 グループを作成するように求められます。 **[グループの作成]** を選択してグループを作成します。 これを行う必要があるのは予約予定表に対して 1 回のみです。)

フォームを操作するときは、次の点に注意してください。

- 予定の種類に既にリンクされているフォームを変更するには、予定の種類から、または [https://forms.office.com](https://forms.office.com) で Microsoft 365 グループ内からフォームを選択します。
- [ファイルアップロードに関する質問](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf)を含むフォームへのファイルのアップロードは、すべての出席者が同じ組織に所属する場合にサポートされます。

スケジュール管理者が予定の種類を使用して予定をスケジュールする場合、フォームを含めるか、削除するか、それとも予定の種類にリンクされたその他のフォームを追加するかを選択できます。 出席者は、予定に参加する前にフォームに入力する必要があります。

> [!NOTE]
> 医療提供者の場合、医療提供者または患者が Teams (Forms アプリ、Bookings アプリ、会議記録 (有効になっている場合)、およびその他の Teams 仮想予定サービス) で提供された情報で、医療記録の継続または保持の目的で必要な情報は、医療提供者がダウンロード、コピー、および注記する必要があります。 このサービスは、法的な医療記録または指定された記録セットを保持するものではありません。

詳細については、「[予定の種類を作成する](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)」を参照してください。

## <a name="schedule-an-appointment"></a>予定を設定する

予約カレンダーで、**[新しい予約]** を選択します。 予定の種類を選択し、関連する情報を入力します。

これには、出席者の連絡先情報、サービスを提供するスタッフ メンバー、スタッフだけが表示できる内部メモ、メール リマインダー、出席者がモバイル ブラウザーから参加できるかどうかが含まれます。 フォームが予定の種類にリンクされている場合、フォームを含めるか、削除するか、それともリンクされたその他のフォームを追加するかを選択できます。

出席者に送信される確認メールには、会議のリンクと、仮想予定を予定表に追加するための添付ファイルが含まれています。 スタッフには、確認メールと会議出席依頼も届きます。 フォームを予定に含める場合、Bookings 管理者とスケジュール管理者は、予定の前に出席者がフォームを完了したかどうかを確認し、出席者の回答を表示できます。

詳細については、「[Teams の予約アプリで予約をスケジュールする](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)」を参照してください。

## <a name="conduct-an-appointment"></a>予定を実施します

Teams または Outlook 予定表で予約に移動し、**[参加]** または Teams 会議リンクを選択します。 オーディオとビデオの設定を確認し、**[今すぐ参加]** を選択します。 詳細については、「[Bookings の予定を行う](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)」を参照してください。

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>予定を監視し、リアルタイムの状態の更新を取得する

Bookings の [キュー ビュー](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) では、スタッフがその日のすべての仮想予定を監視するための、リアルタイムで更新されるダッシュボードが提供されます。 キューを表示するには、Bookings の **[キュー]** タブに移動します。

:::image type="content" source="media/bookings-virtual-visits-queue.png" alt-text="Teams の Bookings アプリのキュー ビューのスクリーンショット" lightbox="media/bookings-virtual-visits-queue.png":::

キューでは、スケジュール管理者が新しい予約を追加し、関連する予定の詳細を表示し、その日全体の予定の状態を確認できます。 患者が待機室に参加すると、状態が変更され、待機時間が表示および追跡されます。 変更を簡単に識別できるように、ビューは自動的に更新され、色分けされます。

スタッフは、予定の参加や管理をキューから直接行うこともできます。

> [!NOTE]
> 現在、Bookings アプリでは、1 つの予約予定表あたり最大 100 人のスタッフを追加できます。 Graph API を使用して予約予定表にスタッフを設定および追加した場合、この制限は適用されない可能性があります。 このシナリオでは、スタッフが 100 人を超える予定表のコンテンツを **[キュー]** タブでレンダリングすることはできません。 最適なエクスペリエンスを得るには、予約予定表に追加するスタッフを 100 人以下にすることをお勧めします。 現在、今後のリリースでこの制限を解消できる作業を行っています。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web アプリを使用したその他の機能

Bookings Web アプリでは、追加機能が用意されています。 たとえば、セルフサービスのオンライン予約ページを公開して、スタッフと一緒に予定をスケジュールできます。 Bookings Web アプリにアクセスするには、[**その他のオプション** (...)] > **[Bookings Web アプリを開く]** に移動します。

詳細については、「[Microsoft Bookings](/microsoft-365/bookings/bookings-overview)」を参照してください。

## <a name="get-insight-into-virtual-appointments-usage"></a>仮想予定の使用状況に関する分析情報を取得する

Microsoft Teams 管理センターの [[仮想訪問の使用状況レポート]](virtual-visits-usage-report.md) では、管理者が組織内の Teams 仮想予定アクティビティの概要を確認できます。 このレポートには、Bookings の予定を含む仮想予定の詳細な分析が表示されます。

ロビーの待機時間や予定の期間などの主要なメトリックを表示できます。 この情報を使用して使用状況の傾向を把握し、仮想予定を最適化してビジネス成果を向上させるために役立ちます。

## <a name="related-articles"></a>関連記事

- [ブラウザーで Teams 仮想予定の参加エクスペリエンスを管理する](browser-join.md)

- [Teams 仮想訪問の使用状況レポート](virtual-visits-usage-report.md)

- [医療関係組織のための Teams の使用を開始する](teams-in-hc.md)

- [Teams の Bookings アプリのヘルプ ドキュメント](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
