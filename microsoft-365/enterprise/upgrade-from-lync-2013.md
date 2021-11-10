---
title: Lync Server 2013 からのアップグレード
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: Lync Server 2013 からアップグレードする情報とリソースを検索します。 サポートは 2023 年 4 月 11 日に終了します。
ms.openlocfilehash: a770ce6acab4320bc84e920b1c527e9c63e72bbb
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889907"
---
# <a name="upgrading-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Microsoft Lync Server 2013 は **、2023** 年 4 月 11 日にサポートが終了します。 この記事では、既存の Lync Server 展開をオンプレミスまたはオンプレミスのMicrosoft TeamsまたはSkype for Businessするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>サポート終了 *とは何ですか*?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあります。その間、新機能、バグ修正、セキュリティ修正などをご利用ください。 サポート終了日が終わると、製品は動作を停止しますが、Microsoft は次の機能を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品のそれ以上の更新プログラム、パッチ、または修正プログラム (セキュリティ パッチ/修正プログラムを含む) はありません。 Microsoft サポートは、サポートの取り組みを、より新しいバージョンに完全に移行します。

## <a name="plan-ahead"></a>計画を立て

サポートが終了する日付を製品ライフサイクル [サイトで確認します](/lifecycle/products/lync-server-2013)。 これらの日付を念頭に置いてアップグレードまたは移行を計画します。 記載されている日付 *で製品の* 動作が停止しない場合があります。 ただし、インストールは、その日付以降に修正プログラムが適用されなくなるので、製品の次のバージョンへのスムーズな移行を計画する必要があります。 次の表に、使用可能なオプションの一覧を示します。

|サポート製品の終了|サポート|推奨|
|---|---|---|
|Lync Server 2013|2015 Skype for Business Server 2019 へのアップグレード|Microsoft Teams へアップグレードする

## <a name="whats-next"></a>次の手順

サーバーにアップグレードすることをお勧Microsoft Teams。 Microsoft Teams Lync Server の機能を拡張し、チャット、会議、通話、コラボレーション、アプリ統合、ファイル ストレージを 1 つのインターフェイスにまとめます。 Teamsを効率化し、ユーザーの満足度を向上し、ビジネスの成果を加速します。 Microsoft では、継続的に Teams の機能を拡張することで、新しい方法でユーザーがコミュニケーションと共同作業を行えるよう、組織的および地理的な障壁を壊してプロセスと意思決定の効率性を高めます。

2015 または 2019 Microsoft Teamsにアップグレードできない場合Skype for Business Serverアップグレードできます。 これらの製品の両方が 2025 年 10 月 14 日にサポート終了に達する点を知る重要な計画上の考慮事項です。 詳細については、次のサポート ライフサイクル ページを参照してください。

- [Skype for Business Server 2015 サポート ライフサイクル情報](/lifecycle/products/skype-for-business-server-2015)
- [Skype for Business Server 2019 サポート ライフサイクル情報](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>Microsoft Teams へアップグレードする

オンプレミスの展開からMicrosoft Teamsアップグレードに関する詳細なガイダンスがあります。 まず、主要な技術的要件について説明します。 ハイブリッド接続を確立する Teams必要があります。 [ハイブリッド接続を計画すると](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 、ハイブリッドのセットアップの概要が示されます。 この記事では、Lync Server 2013 にもSkype for Businessに焦点を当て、すべての概念が適用されます。 Lync [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements) Server 2013 固有の詳細については、「サーバーのバージョン要件」セクションを参照してください。

また、Lync Server 2013 の展開を完全に最新の環境に更新する必要があります。 [Lync Server 2013](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164)のすべての最新の更新プログラムの一覧を公開しますが、次の更新プログラムは、Lync Server 2013 へのアップグレードの前提条件Microsoft Teams。

- [Lync Server 2013 の 2021 年 9 月の累積的な更新プログラム 5.0.8308.1149](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043)Core Components : この更新プログラムは、オンプレミスユーザーを Microsoft Teams に移動するために使用されるコマンドレットの OAuth 認証プロトコルに Live ID 認証を置き換える。 `Move-CSUser`

Lync のユーザー エクスペリエンスMicrosoft Teamsはるかに優れても、大幅に異なります。 したがって、組織とユーザーを準備して、組織の迅速な導入を確実に行うMicrosoft Teams。 組織を準備し、組織へのアップグレードを計画し、Teamsを確実にロールアウトする方法に関する豊富な情報が用意されています。 

**最初に [Teams、](/MicrosoftTeams/upgrade-skype-teams)** テクニカル 情報、トレーニング リソース、Ignite セッションへのリンク、利用可能なヘルプ リソース、ケース スタディなどをご覧ください。

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="アップグレード ポータルTeamsスクリーンショット":::

### <a name="upgrade-to-skype-for-business-server"></a>Skype for Business Server へのアップグレード

アップグレードするSkype for Business Serverのパスは、アップグレードするバージョンによって異なります。 Skype for Business Server 2015 では、Lync Server 2013 からの一時アップグレードがサポートされています。 一方、Skype for Business Server 2019 にアップグレードするには、最初に Skype for Business Server 2019 を Lync Server 2013 組織に導入し、新しいサーバーに操作を転送する必要があります。 

考慮すべき重要な点の 1 つは、各製品の現在のサポート フェーズである Skype for Business 2019 がメインストリーム サポートであり、Skype for Business 2015 が現在拡張サポート中である点です。  したがって、2019 年に 2019 Skype for Business Serverすることをお勧めします。 メインストリームサポートと拡張サポートの違いの詳細については、「固定ライフサイクル ポリシー」 [を参照してください](/lifecycle/policies/fixed)。

各アップグレード シナリオの詳細については、次のリソースを参照してください。

- [2019 Skype for Business Serverへのアップグレード](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [2015 Skype for Business Serverへのアップグレード](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
