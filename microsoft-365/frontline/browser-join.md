---
title: ブラウザーで Teams 仮想予定の参加エクスペリエンスを管理する
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
ms.reviewer: hafarmer
description: ブラウザーでの Teams 仮想予定の参加エクスペリエンスについて説明します。
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 869e554ed202f5e2ef24cf75e3dc2338c65de554
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994820"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>ブラウザーで Teams 仮想予定の参加エクスペリエンスを管理する

Microsoft Teams を使用すると、Teams をダウンロードしなくても、仮想予定に簡単に参加できます。 よりシームレスなエクスペリエンスを実現するために、出席者は、デスクトップまたはモバイル ブラウザーから、医療訪問や財務コンサルテーションなどの予定に参加できます。 出席者は、デバイスに Teams アプリをインストールする必要はありません。

ブラウザーへの参加では、出席者が予定に参加するときに、Teams のダウンロードを求めるメッセージは表示されません。 代わりに、Teams がモバイル ブラウザーで開き、出席者は **[今すぐ参加]** を選択できます。 この機能では、Teams がデバイスに既にインストールされている場合、Teams はアプリではなくブラウザーで開かれることに注意してください。

現在、ブラウザーの参加は、次を通じてスケジュールされた予定で使用できます。

- [Bookings アプリ](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams 電子カルテ (EHR) コネクタ

  - [Cerner EHR](ehr-admin-cerner.md) との統合
  - [エピック EHR](ehr-admin-epic.md) との統合

## <a name="set-up-browser-join"></a>ブラウザー結合を設定する

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings アプリを通じてスケジュールされた予定

組織内のスケジューラは、特定の予定の種類と Bookings アプリの個々の予定に対して、この機能を有効にすることができます。

この機能を有効にすると、出席者に送信される確認メールまたは SMS テキストに、デスクトップまたはモバイル ブラウザーで Teams を開く会議参加リンクが含まれます。 サポートされているブラウザーの一覧については、「[サポートされているブラウザー](#supported-browsers)」を参照してください。

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>予定の種類に対してブラウザーの参加を有効にする

Bookings で **[設定]** > **[予定の種類]** に移動し、[[予定の種類]](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) を選択して、**[出席者にブラウザーからの参加を許可する]** をオンにします。 これを行うと、この種類のすべての予定に対するブラウザー参加が有効になります。

:::image type="content" source="media/browser-join-bookings-appointment-type.png" alt-text="Bookings アプリの予定の種類に対するブラウザー設定からの出席者の参加を許可する設定のスクリーンショット":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>個々の予定のブラウザー参加を有効にする

Bookings で **[新しい予約]** を選択し、**[出席者がブラウザーから参加することを許可する]** をオンにします。

:::image type="content" source="media/browser-join-bookings-form.png" alt-text="Bookings アプリの新しい予約フォームのブラウザー設定から出席者の参加を許可する設定のスクリーンショット":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Teams EHR コネクタを使用してスケジュールされた予定

お客様またはスタッフによるセットアップは不要です。

**Cerner EHR との統合**: Teams EHR コネクタは、SMS テキスト メッセージ内のリンクを介して仮想予定に参加する患者をサポートします。 予定の時点で、患者は SMS テキスト メッセージのリンクをタップして参加でき、Teams はブラウザーで開きます。

**エピック EHR との統合**: Teams EHR コネクタは、MyChart Web とモバイルを介して仮想予定に参加する患者をサポートします。 予定の時点で、患者は **[仮想訪問の開始]** ボタンを使用して MyChart から予定を開始でき、Teams はブラウザーで開きます。

## <a name="supported-browsers"></a>サポートされるブラウザー

現在サポートされているブラウザーを次に示します。 特に明記されていない限り、最新バージョンと 2 つの以前のバージョンがサポートされています。

|プラットフォーム  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; 発信画面の共有は、iOS または Android ではサポートされていません。

&sup2; Safari 上の iOS アプリでは、マイクデバイスとスピーカー デバイスを選択できません。 たとえば、Bluetooth デバイスなどです。 これは、既定のデバイス選択を制御するオペレーティング システムの制限です。

## <a name="things-to-consider"></a>考慮事項

予定を実施するスタッフ メンバーは、Teams デスクトップ、モバイル、または Web クライアントから、デスクトップまたはモバイル ブラウザーから参加する出席者と画面を共有できます。 ただし、出席者はデスクトップまたはモバイル ブラウザーから画面を共有することはできません。

## <a name="related-articles"></a>関連記事

- [Teams と Bookings を使用した仮想予定](bookings-virtual-visits.md)
- [Bookings の予定の種類を作成する](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Bookings の予定を出席者として参加させる](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Teams での仮想予定 - Cerner EHR への統合](ehr-admin-cerner.md)
- [Teams での仮想アクセス - Epic EHR への統合](ehr-admin-epic.md)
