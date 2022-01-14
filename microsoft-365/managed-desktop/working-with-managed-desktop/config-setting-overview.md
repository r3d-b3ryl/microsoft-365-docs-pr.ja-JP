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
ms.openlocfilehash: dcfa702511f5b1047b4d40b36e1466b6e08749fc
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62033263"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>構成可能な設定 - Microsoft マネージド デスクトップ

Microsoft Managed Desktop は、Microsoft Managed Desktop によって管理されるすべてのデバイスに適用される設定とポリシーを展開します。 詳細については、「デバイス構成 [」を参照してください](../service-description/device-policies.md)。

Microsoft Managed Desktop の構成可能な設定を使用すると、IT 管理者は組織やビジネス ニーズに固有の設定をカスタマイズして展開できます。 これらの設定は、Microsoft Managed Desktop によって管理されるデバイス構成設定とポリシーに加えてです。  

構成可能な設定の変更はクラウドで行い、定義済みの展開グループ内の Microsoft Managed Desktop デバイスに適用されます。 このプロセスは、Microsoft Managed Desktop が、サービスによって定義および管理されるデバイス構成設定とポリシーの変更を管理する方法に似ています。 Microsoft Managed Desktop が変更の展開に使用するのと同じプロセスを使用して、最新の IT 管理プラクティスを使用して組織を前進します。

## <a name="when-to-use-configurable-settings"></a>構成可能な設定を使用する場合

構成可能な設定を使用するには、いくつかの時間があります。 

**オンボーディング プロセス** – Microsoft Managed Desktop サービスにオンボードする場合、または多数のデバイス (20 台以上) をオンボードする場合は、構成可能な設定をカスタマイズする必要があります。 カテゴリの設定は、Microsoft Managed Desktop 管理ポータルで構成されます。 オンボーディングを完了して管理ポータルにアクセスしたら、組織に合わせてカスタマイズする設定カテゴリを決定し、変更を加え、展開を行い、変更を展開できます。

**設定を維持** する - 設定を定期的に確認し、必要な更新を行います。 ビジネスの変更をサポートするために変更を加える必要がある場合があります。   

## <a name="setting-categories"></a>カテゴリの設定

カスタマイズできる構成可能な設定カテゴリを次に示します。
- [デスクトップの背景画像](config-setting-ref.md#desktop-background-picture) – Microsoft Managed Desktop デバイスのデスクトップの背景画像をカスタマイズします。 
- [ブラウザーの開始ページ](config-setting-ref.md#browser-start-pages)– スタート ページを追加して、ブラウザーで使用Microsoft Edge。 「ブラウザーの開始ページ」を参照してください。
- [Enterpriseモード サイト一覧](config-setting-ref.md#enterprise-mode-site-list-location)– サイトとその互換モードを追加します。 リスト上のサイトは、Internet Explorer。 
- [信頼済みサイト](config-setting-ref.md#trusted-sites) – 信頼できるサイトを追加し、各サイトのセキュリティ ゾーンを設定します。 
- [プロキシ サイトの例外](config-setting-ref.md#proxy) – プロキシ サーバーのアドレス番号とポート番号を設定し、プロキシ サイトの例外を追加します。

各設定カテゴリは、独自にカスタマイズおよび展開できます。 複数の設定カテゴリに同時に変更を展開することもできますが、設定カテゴリには一度に 1 つの変更のみを展開できます。

次に例を示します。
- デスクトップの背景画像と信頼できるサイトに対する変更を、それぞれ独自の展開として同時に展開できます。 
- 2 つの展開をブラウザーのスタート ページに同時に展開できない。 最新の展開では、まだ進行中の以前の展開が停止します。

## <a name="configurable-setting-process"></a>構成可能な設定プロセス

Microsoft Managed Desktop では、組織で構成可能な設定を利用する場合、次のようなプロセスを実行する必要があります。

**手順 1 - 計画** - 構成可能な設定について学び、組織に構成する設定カテゴリを決定します。 各グループに変更を展開する場合のタイムラインを作成します。 内部の変更管理プロセスを満たすユーザーへの通信を計画します。 たとえば、ブラウザーの開始ページを追加する場合は、展開後にブラウザーに新しいスタート ページのセットが含まれます。  

**手順 2 - 展開の構成とステージ** - Microsoft Managed Desktop 管理ポータルで構成可能な設定を変更します。 展開の準備が整った状態で変更を行います。 変更点と、変更によってデバイスのエクスペリエンスがどのように変化するのかについて、ユーザーに知らせておく必要があります。   

Microsoft Managed Desktop 管理ポータルで変更を構成およびステージします。 詳細については、「構成可能な設定を [カスタマイズする」を参照してください](config-setting-ref.md)。 

**手順 3 - 変更を伝える** 今後の変更に関する情報をユーザーに伝えます。 展開ごとに、変更管理プロセスの一部である通信を完了します。 ユーザーの動作やデバイスに表示される動作に影響を与える変更を明確に伝える必要があります。

**手順 4 - 変更を展開する** - テスト グループから始まる変更を展開します。 テスト グループを使用すると、デバイスが少ないグループ内の問題を検証およびトラブルシューティングしてから、より大きなデバイス グループに変更を展開できます。 問題が発生した場合は、変更を元に戻し、設定を更新し、新しい展開を展開できます。 Microsoft Managed Desktop では、構造化されたアプローチに従い、次の順序でグループに展開してください。テスト、ファースト、Fast、および Broad。   

構成可能なすべての設定は、Microsoft Managed Desktop 管理ポータルを使用して管理されます。 詳細については、「変更の展開 [」を参照してください](config-setting-deploy.md)。 

**手順 5 - 変更の追跡** – 展開状態での変更の進行状況を追跡します。 設定ごとに、次の機能を使用できます。
- **進行状況の追跡** – 変更を展開した後の状態を追跡します。 状態は [進行中] **に変更され**、[完了] または **[失敗**] **に変わります**。 展開が失敗した場合、Microsoft Managed Desktop Operations のサポート要求が自動的に開き、問題を調査します。  
- **「展開されたバージョン」を参照** してください。 展開された各変更にはバージョン番号があります。
- **変更を** 元に戻す – 変更を元に戻すと、現在の展開が停止し、すべてのグループがすべてのグループに展開された最後の変更に戻されます。 最後に既知の良好な設定値にロールバックします。
- **変更の検証** - 展開が完了したら、変更が期待した通り適用されたのを検証します。  

展開が失敗した場合、または変更を元に戻すできない場合は[](admin-support.md)、Microsoft Managed Desktop Operations を使用してサポート 要求を開きます。 

詳細については、「構成可能な設定 [の展開と追跡」を参照してください](config-setting-deploy.md)。

## <a name="additional-resources"></a>その他のリソース
- [構成可能な設定のリファレンス](config-setting-ref.md) 
- [構成可能な設定を展開する](config-setting-deploy.md) 
