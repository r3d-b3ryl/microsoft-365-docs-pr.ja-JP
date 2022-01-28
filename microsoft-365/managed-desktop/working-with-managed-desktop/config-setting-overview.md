---
title: Microsoft Managed Desktop の構成可能な設定
description: Microsoft Managed Desktop を使用した構成可能な設定に関する情報
keywords: Microsoft Managed Desktop、Microsoft 365、サービス、ドキュメント、設定、構成可能な設定
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 910bd8d37853ce70acb6379599b0259446b0752e
ms.sourcegitcommit: 2c3b737e71038f843ef9e9ff4d5b99d6110b8ec5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2022
ms.locfileid: "62265669"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>構成可能な設定 - Microsoft マネージド デスクトップ

Microsoft Managed Desktop は、Microsoft Managed Desktop によって管理されるすべてのデバイスに適用される設定とポリシーを展開します。 詳細については、「デバイス構成 [」を参照してください](../service-description/device-policies.md)。

Microsoft Managed Desktop の構成可能な設定を使用すると、IT 管理者は組織やビジネス ニーズに固有の設定をカスタマイズして展開できます。 これらの設定は、Microsoft Managed Desktop によって管理されるデバイス構成設定とポリシーに加えてです。  

構成可能な設定の変更は、クラウドで行います。 定義された展開グループ内の Microsoft Managed Desktop デバイスに適用されます。 このプロセスは、Microsoft Managed Desktop が、サービスによって定義および管理されるデバイス構成設定とポリシーの変更を管理する方法に似ています。 Microsoft Managed Desktop が変更の展開に使用するのと同じプロセスを使用して、最新の IT 管理プラクティスを使用して組織を前進します。

## <a name="when-to-use-configurable-settings"></a>構成可能な設定を使用する場合

構成可能な設定は、次のシナリオで使用します。

| シナリオ | 説明 |
| ------ | ------ |
| オンボーディング プロセス | Microsoft Managed Desktop では、Microsoft Managed Desktop サービスにオンボードする場合、または多数のデバイス (20 台以上) をオンボードする場合に、構成可能な設定をカスタマイズする必要があります。 <br><br>カテゴリの設定は、Microsoft Managed Desktop 管理ポータルで構成されます。 オンボードして管理ポータルにアクセスした後、組織に合わせてカスタマイズする設定カテゴリを決定できます。 その後、変更を行い、展開をステージし、変更を展開します。 |
| 設定を維持する | 設定を定期的に確認し、必要な更新を行います。 ビジネスの変更をサポートするために変更を加える必要がある場合があります。 |

## <a name="setting-categories"></a>カテゴリの設定

カスタマイズできる構成可能な設定カテゴリを次に示します。

| カテゴリ | 説明 |
| ------ | ------ |
| [デスクトップの背景画像](config-setting-ref.md#desktop-background-picture) | Microsoft Managed Desktop デバイスのデスクトップの背景画像をカスタマイズします。 |
| [ブラウザーの開始ページ](config-setting-ref.md#browser-start-pages) | スタート ページを追加して、Microsoft Edge。 |
| [Enterprise モード のサイト一覧](config-setting-ref.md#enterprise-mode-site-list-location) | サイトとその互換モードを追加します。 リスト上のサイトは、Internet Explorer。 |
| [信頼済みサイト](config-setting-ref.md#trusted-sites) | 信頼できるサイトを追加し、各サイトのセキュリティ ゾーンを設定します。 |
| [プロキシ サイトの例外](config-setting-ref.md#proxy) | プロキシ サーバーのアドレス番号とポート番号を設定し、プロキシ サイトの例外を追加します。 |

各設定カテゴリは、独自にカスタマイズおよび展開できます。 複数の設定カテゴリに同時に変更を展開できます。 ただし、設定カテゴリには一度に 1 つの変更のみを展開できます。

例:

- デスクトップの背景画像と信頼できるサイトに対する変更を、それぞれ独自の展開として同時に展開できます。
- 2 つの展開をブラウザーのスタート ページに同時に展開できない。 最新の展開では、まだ進行中の以前の展開が停止します。

## <a name="configurable-setting-process"></a>構成可能な設定プロセス

Microsoft Managed Desktop では、組織で構成可能な設定を使用する場合、以下のようなプロセスに従ってください。

| 手順  | プロセス |
| ------ | ------ |
| **手順 1 : 計画** | <ol type="1"><li>構成可能な設定について学び、組織に構成する設定カテゴリを決定します。</li> <li>各グループに変更を展開する場合は、タイムラインを作成します。</li> <li>内部の変更管理プロセスを満たすユーザーへの通信を計画します。 たとえば、ブラウザーの開始ページを追加する場合は、展開後にブラウザーに新しいスタート ページセットが追加されるユーザーに通知します。</li></ol> |
| **手順 2: 展開の構成とステージ** | <ol type="1"><li>Microsoft Managed Desktop 管理ポータルで構成可能な設定を変更します。</li><li>展開の準備が整った状態で変更を行います。</li> <li>変更点と、変更によってデバイスのエクスペリエンスがどのように変化するのかについて、ユーザーに通知してください。</li><li>Microsoft Managed Desktop 管理ポータルで変更を構成およびステージします。 詳細については、「構成可能な設定を [カスタマイズする」を参照してください](config-setting-ref.md)。</li></ol>|
| **手順 3: 変更を伝える** | <ol type="1"><li>今後の変更に関する情報をユーザーに伝えます。</li> <li>展開ごとに、変更管理プロセスの一部である通信を完了します。 ユーザーの動作やデバイスに表示される動作に影響を与える変更を明確に伝える必要があります。</li></ol> |
| **手順 4: 変更を展開する** | テスト グループから始まる変更を展開します。 テスト グループを使用すると、デバイスが少ないグループ内の問題を検証およびトラブルシューティングしてから、より大きなデバイス グループに変更を展開できます。 <br><br>問題が発生した場合は、変更を元に戻し、設定を更新し、新しい展開を展開できます。 Microsoft Managed Desktop では、構造化されたアプローチに従い、次の順序でグループに展開してください。テスト、ファースト、Fast、および Broad。 <br><br>構成可能なすべての設定は、Microsoft Managed Desktop 管理ポータルを使用して管理されます。 詳細については、「変更の展開 [」を参照してください](config-setting-deploy.md)。 |
| **手順 5: 変更の追跡** | [展開の状態] セクションで変更の進行状況を追跡します。 設定ごとに、次の機能を使用できます。 <ul><li>**進捗の追跡:**  変更を展開した後の状態を追跡します。 状態は [進行中] **に変更され**、[完了] または **[失敗**] **に変わります**。 展開が失敗した場合、Microsoft Managed Desktop Operations のサポート要求が自動的に開き、問題を調査します。</li> <li>**「展開されているバージョン」を参照してください。** 展開された各変更にはバージョン番号があります。</li><li>**変更を元に戻す:** 変更を元に戻すと、現在の展開が停止します。 すべてのグループを、すべてのグループに展開された最後の変更に戻します。 最後に既知の良好な設定値にロールバックします。</li><li>**変更の検証:** 展開が完了したら、変更が予想通り適用されたのを検証します。</li></ul> |

展開に失敗した場合、または変更を元に戻すできない場合[](admin-support.md)は、Microsoft Managed Desktop Operations を使用してサポート 要求を開きます。

詳細については、「構成可能な設定 [の展開と追跡」を参照してください](config-setting-deploy.md)。

## <a name="additional-resources"></a>その他のリソース

- [構成可能な設定のリファレンス](config-setting-ref.md)
- [構成可能な設定を展開する](config-setting-deploy.md)
