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
description: Lync Server 2013 からアップグレードする情報とリソースを確認します。 サポートは 2023 年 4 月 11 日に終了します。
ms.openlocfilehash: 925b53d751cd559ce3ccdf28d823531021611551
ms.sourcegitcommit: 997eb64f80da99b1099daba62994c722bbb25d72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66129143"
---
# <a name="upgrading-from-lync-server-2013"></a>Lync Server 2013 からのアップグレード

Microsoft Lync Server 2013 は、 **2023 年 4 月 11** 日にサポートを終了します。 この記事では、既存の Lync Server 展開をオンプレミスのMicrosoft TeamsまたはSkype for Businessにアップグレードするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>*サポートの終了* とは何ですか?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあり、その間に新機能、バグ修正、セキュリティ修正などが行われます。 サポート終了日を経過しても、製品の動作は停止しませんが、Microsoft では次のものが提供されなくなります。

- 発生する可能性がある問題のテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。

- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品の更新プログラム、パッチ、修正プログラム (セキュリティ パッチや修正プログラムを含む) は今後ありません。 Microsoft サポートは、サポート作業をより新しいバージョンに完全に移行する予定です。

## <a name="plan-ahead"></a>事前に計画する

[製品ライフサイクル サイト](/lifecycle/products/microsoft-lync-server-2013)でサポートが終了する日付を確認します。 これらの日付を念頭に置いて、アップグレードまたは移行を計画します。 製品が一覧に表示された日付に *動作を停止することはないことを忘れないでください* 。 ただし、インストールはその日以降修正プログラムが適用されなくなるので、次のバージョンの製品へのスムーズな移行を計画する必要があります。 次の表に、使用可能なオプションの一覧を示します。

|サポート製品の終了|サポート|推奨|
|---|---|---|
|Lync Server 2013|Skype for Business Server 2015 または 2019 にアップグレードする|Microsoft Teams へアップグレードする

## <a name="whats-next"></a>次の手順

Microsoft Teamsにアップグレードすることをお勧めします。 Microsoft Teamsでは、Lync Server の機能が拡張され、チャット、会議、通話、コラボレーション、アプリ統合、ファイル ストレージが 1 つのインターフェイスにまとめられます。 Teamsは、ユーザーの作業を効率化し、ユーザーの満足度を向上し、ビジネス成果を加速するのに役立ちます。 Microsoft では、継続的に Teams の機能を拡張することで、新しい方法でユーザーがコミュニケーションと共同作業を行えるよう、組織的および地理的な障壁を壊してプロセスと意思決定の効率性を高めます。

Microsoft Teamsにアップグレードできない場合は、Skype for Business Server 2015 または 2019 にアップグレードできます。 重要な計画上の考慮事項は、これらの製品の両方が 2025 年 10 月 14 日にサポート終了になるということです。 詳細については、次のサポート ライフサイクル ページを参照してください。

- [Skype for Business Server 2015 サポート ライフサイクル情報](/lifecycle/products/skype-for-business-server-2015)
- [Skype for Business Server 2019 サポート ライフサイクル情報](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>Microsoft Teams へアップグレードする

オンプレミスのデプロイからMicrosoft Teamsへのアップグレードに関する詳細なガイダンスがあります。 最初に、いくつかの主要な技術的要件について説明します。 ハイブリッド接続を確立する必要があります。これにより、ユーザーをTeamsに移動できるようになります。 [ハイブリッド接続を計画](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) すると、ハイブリッド環境のセットアップの概要が示されます。 この記事はSkype for Businessに焦点を当てていますが、すべての概念は Lync Server 2013 にも当てはまります。 Lync Server 2013 固有の詳細については、 [サーバーのバージョン要件](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements) に関するセクションを参照してください。

また、Lync Server 2013 の展開が完全に最新であることを確認する必要もあります。 [Lync Server 2013 のすべての最新の更新プログラムの一覧](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164)を公開しますが、次の更新プログラムは、Microsoft Teamsへのアップグレードの前提条件です。

- [2021 年 9 月の累積的な更新プログラム 5.0.8308.1149 for Lync Server 2013 Core Components](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043): この更新プログラムは、オンプレミス ユーザーをMicrosoft Teamsに移行するために使用されるコマンドレットの OAuth 認証プロトコル`Move-CSUser`にライブ ID 認証を置き換えます。

Microsoft Teamsのユーザー エクスペリエンスは Lync よりはるかに豊富で優れていますが、これも大幅に異なります。 そのため、Microsoft Teamsの迅速な導入を確実にするために、組織とユーザーを準備する必要もあります。 組織を準備し、Teamsへのアップグレードを計画し、ロールアウトを成功させる方法に関する豊富な情報を入手できます。

技術情報、トレーニング リソース、Ignite セッションへのリンク、利用可能なヘルプ リソース、ケース スタディなどを見つけることができる、**[Teams アップグレード ポータル](/MicrosoftTeams/upgrade-skype-teams)から開始することをお勧めします**。

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="Teams アップグレード ポータルのスクリーンショット":::

### <a name="upgrade-to-skype-for-business-server"></a>Skype for Business Server へのアップグレード

Skype for Business Serverへのパスは、アップグレード先として選択したバージョンによって異なります。 Skype for Business Server 2015 では、Lync Server 2013 からのインプレース アップグレードがサポートされます。 一方、Skype for Business Server 2019 にアップグレードするには、最初に 1 つ以上の新しいサーバーを追加して Lync Server 2013 のインストールに 2019 Skype for Business Serverを導入してから、追加した新しい 2019 サーバーに操作を転送する必要があります。

考慮すべき重要な点の 1 つは、各製品の現在のサポート フェーズです。Skype for Business 2019 はメインストリーム サポートであり、Skype for Business 2015 は現在延長サポート中です。  そのため、Skype for Business Server 2019 にアップグレードすることをお勧めします。 メインストリームサポートと拡張サポートの違いの詳細については、「 [固定ライフサイクル ポリシー」を](/lifecycle/policies/fixed)参照してください。

各アップグレード シナリオの詳細については、次のリソースを参照してください。

- [Skype for Business Server 2019 にアップグレードする](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [Skype for Business Server 2015 にアップグレードする](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
