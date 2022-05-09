---
title: Microsoft 365中国ユーザー向けのグローバル テナント パフォーマンスの最適化
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: この記事では、グローバル Microsoft 365 テナントの中国ユーザー向けのネットワーク パフォーマンスを最適化するためのガイダンスを提供します。
ms.openlocfilehash: 6c99245d523048d30124fc8f8b0c01d7c2004327
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326931"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365中国ユーザー向けのグローバル テナント パフォーマンスの最適化

> [!IMPORTANT]
> このガイダンスは、**中国にあるエンタープライズ Microsoft 365 ユーザー** が **グローバル Microsoft 365 テナント** に接続する使用シナリオに固有です。 このガイダンスは、21Vianet によって運用Office 365テナント **には適用されません**。

>[!NOTE]
>この記事は、リモート ユーザーの最適化Microsoft 365対処する一連の記事の一部です。

>- VPN 分割トンネリングを使用してリモート ユーザーのMicrosoft 365接続を最適化する方法の概要については、「[概要: Microsoft 365の VPN 分割トンネリング」を](microsoft-365-vpn-split-tunnel.md)参照してください。
>- VPN 分割トンネリングの実装に関する詳細なガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。
>- VPN 分割トンネリングのシナリオの詳細な一覧については、「[Microsoft 365の一般的な VPN 分割トンネリング シナリオ」を](microsoft-365-vpn-common-scenarios.md)参照してください。
>- VPN 分割トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN 分割トンネリング[のメディア トラフィックTeamsセキュリティ保護](microsoft-365-vpn-securing-teams.md)する」を参照してください。
>- VPN 環境で Stream イベントとライブ イベントを構成する方法については、「VPN 環境での [Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)」を参照してください。

グローバル Microsoft 365 テナントを持ち、中国に企業が存在する企業の場合、中国ベースのユーザーのクライアント パフォーマンスMicrosoft 365、中国電話会社のインターネット アーキテクチャに固有の要因によって複雑になる可能性があります。

中国 ISP は、高度な境界ネットワーク混雑を起こしやすい境界デバイスを通過するグローバルパブリック インターネットへの海洋接続を規制しています。 この混雑により、中国に出入りするすべてのインターネット トラフィックのパケット損失と待機時間が生じます。

![Microsoft 365 トラフィック - 最適化されていません。](../media/O365-networking/China-O365-unoptimized.png)

パケットの損失と待機時間は、ネットワーク サービスのパフォーマンス、特に大規模なデータ交換 (大規模なファイル転送など) を必要とするサービス、またはほぼリアルタイムのパフォーマンス (オーディオおよびビデオ アプリケーション) を必要とするサービスに悪影響を及ぼします。

このトピックの目的は、中国のクロスボーダー ネットワーク混雑がMicrosoft 365 サービスに与える影響を軽減するためのベスト プラクティスを提供することです。 このトピックでは、中国の通信事業者内での複雑なルーティングによる高いパケット待ち時間の問題など、他の一般的な最後の 1 マイルのパフォーマンスの問題には対処しません。

## <a name="corporate-network-best-practices"></a>企業ネットワークのベスト プラクティス

中国のグローバル Microsoft 365 テナントとユーザーを持つ多くの企業は、中国のオフィスの場所と世界中の海洋の場所の間で企業ネットワーク トラフィックを運ぶプライベート ネットワークを実装しています。 これらの企業は、このネットワーク インフラストラクチャを利用して、クロスボーダー ネットワークの混雑を回避し、中国でのMicrosoft 365サービスパフォーマンスを最適化できます。

> [!IMPORTANT]
> すべてのプライベート WAN 実装と同様に、ネットワーク構成が準拠していることを確認するために、お客様の国または地域の規制要件を常に確認する必要があります。

最初のステップとして、[Microsoft 365のネットワーク計画とパフォーマンスのチューニング](./network-planning-and-performance.md)に関するベンチマーク ネットワーク ガイダンスに従う必要があります。 主な目標は、可能であれば、中国のインターネットからグローバル Microsoft 365 サービスにアクセスしないようにすることです。

- 既存のプライベート ネットワークを利用して、中国のオフィス ネットワークと、中国外のパブリック インターネット上で送信される海洋の場所との間でMicrosoft 365ネットワーク トラフィックを伝送します。 中国以外のほぼすべての場所で、明確な利点が得られるでしょう。 ネットワーク管理者は、 [Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)との待機時間の短い相互接続がある領域でエグレスすることで、さらに最適化できます。 香港、シンガポール、日本、韓国が例です。
- VPN 接続を介して企業ネットワークにアクセスするようにユーザー デバイスを構成し、Microsoft 365 トラフィックが企業ネットワークのプライベート な海洋リンクを転送できるようにします。 VPN クライアントが分割トンネリングを使用するように構成されていないか、ユーザー デバイスがMicrosoft 365 トラフィックの分割トンネリングを無視するように構成されていることを確認します。 Teamsおよびリアルタイム メディア トラフィックに対する VPN 接続の最適化の詳細については、[このセクション](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)を参照してください。
- ネットワークを構成して、すべてのMicrosoft 365トラフィックをプライベート の海洋リンクにルーティングします。 プライベート リンク上のトラフィックの量を最小限に抑える必要がある場合は、 **最適化** カテゴリ内のエンドポイントのみをルーティングし、 **Allow** エンドポイントと **Default** エンドポイントに対する要求がインターネットを転送することを許可することを選択できます。 これにより、高待機時間とパケット損失に最も影響を受けやすい重要なサービスに最適化されたトラフィックを制限することで、パフォーマンスが向上し、帯域幅の消費量が最小限に抑えられます。
- 可能であれば、ライブ メディア ストリーミング トラフィック (Teamsなど) に TCP ではなく UDP を使用します。 UDP は、TCP よりも優れたライブ メディア ストリーミング パフォーマンスを提供します。

Microsoft 365 トラフィックを選択的にルーティングする方法については、「[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)」を参照してください。 世界中のすべてのOffice 365 URL と IP アドレスの一覧については、「[Office 365 URL と IP アドレス範囲」を](urls-and-ip-address-ranges.md)参照してください。

![Microsoft 365トラフィック - 最適化されています。](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>ユーザーのベスト プラクティス

企業ネットワークに接続されていない家庭、コーヒー ショップ、ホテル、ブランチ オフィスなどの遠隔地からグローバル Microsoft 365 テナントに接続する中国のユーザーは、デバイスとMicrosoft 365間のトラフィックが中国の混雑したクロスボーダー ネットワーク回線を通過する必要があるため、ネットワーク パフォーマンスが低下する可能性があります。

企業ネットワークへのクロスボーダープライベート ネットワークや VPN アクセスがオプションではない場合でも、中国ベースのユーザーにこれらのベスト プラクティスに従うようにトレーニングすることで、ユーザーごとのパフォーマンスの問題を軽減できます。

- キャッシュをサポートするリッチ Office クライアント (Outlook、Teams、OneDriveなど) を利用し、Web ベースのクライアントを回避します。 クライアント キャッシュ機能とオフライン アクセス機能Office、ネットワークの混雑と待機時間の影響を大幅に軽減できます。
- Microsoft 365 テナントが _電話会議_ 機能で構成されている場合、Teamsユーザーは公衆交換電話網 (PSTN) 経由で会議に参加できます。 詳細については、「[Office 365での電話会議](/microsoftteams/audio-conferencing-in-office-365)」を参照してください。
- ネットワーク パフォーマンスの問題が発生した場合は、トラブルシューティングのために IT 部門に報告し、Microsoft 365 サービスの問題が疑われる場合は Microsoft サポートにエスカレートする必要があります。 すべての問題がクロスボーダー ネットワークのパフォーマンスによって引き起こされるわけではありません。

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Microsoft Teams会議のネットワーク パフォーマンスを中国のユーザーに最適化する

グローバル Microsoft 365 テナントを持ち、中国でプレゼンスを持つ組織の場合、中国ベースのユーザーのクライアント パフォーマンスMicrosoft 365、中国のインターネット アーキテクチャに固有の要因によって複雑になる可能性があります。 多くの企業や学校は、このガイダンスに従って良好な結果を報告しています。 ただし、このスコープは、VPN 接続を備えたオフィスの場所やホーム/モバイル エンドポイントなど、IT ネットワーク設定の制御下にあるユーザー ネットワークの場所に限定されます。 Microsoft Teams通話や会議は、ホーム オフィス、モバイルの場所、道路、コーヒー ショップなどの外部の場所から頻繁に使用されます。 通話と会議はリアルタイムのメディア トラフィックに依存するため、これらのTeamsエクスペリエンスはネットワークの混雑に特に影響を受けます。

その結果、Microsoft は通信プロバイダーと提携し、中国の国内およびパブリック インターネット接続と、Microsoft 365グローバル クラウドのTeamsサービスとSkype サービス間の高品質で優れたネットワーク パスを使用して、オンラインのリアルタイム メディア トラフィックをTeamsおよびSkype for Businessします。 この機能により、パケット損失やその他の主要なメトリックが 10 倍以上向上し、ユーザーのエクスペリエンスに影響が及びます。

>[!IMPORTANT]
>現在、これらの機能強化では、TeamsやMicrosoft Streamを使用した大規模なブロードキャストや "タウンホール" スタイルの会議などの Microsoft Live Events 会議への出席には対応していません。 ライブ イベント会議を表示するには、中国のユーザーがプライベート ネットワークまたは SDWAN/VPN ソリューションを使用する必要があります。 ただし、ネットワークの機能強化は、ライブ イベント会議を発表または作成しているユーザーに役立ちます。これは、その経験がプロデューサーまたは発表者の定期的なTeams会議として機能するためです。

### <a name="organization-network-best-practices-for-teams-meetings"></a>Teams会議の組織ネットワークのベスト プラクティス

これらのネットワークの機能強化を活用する方法を検討する必要があります。これは、クロスボーダー ネットワークの混雑を回避するためにプライベート ネットワーク拡張機能を検討する前のガイダンスを考慮する必要があります。 組織のオフィス ネットワークには、次の 2 つの一般的なオプションがあります。

1. 新しい操作を行う必要はありません。 引き続き、境界を越えた混雑を回避するために、プライベート ネットワーク バイパスに関する以前のガイダンスに従ってください。 リアルタイム メディア トラフィックTeams、以前と同様に、その設定が活用されます。
2. 分割/ハイブリッド パターンを実装します。
   - 会議のTeamsとリアルタイム メディア トラフィックの呼び出しを除き、最適化のフラグが設定されたすべてのトラフィックについては、前のガイダンスを使用します。
   - 会議Teamsルーティングし、パブリック インターネット経由でリアルタイム メディア トラフィックを呼び出します。 リアルタイム メディア ネットワーク トラフィックの識別に関する詳細については、次の情報を参照してください。

高品質の接続を使用するパブリック インターネット経由でリアルタイムのメディア オーディオおよびビデオ トラフィックをTeams送信すると、プライベート ネットワーク経由でトラフィックを送信する場合と無料であるため、コストが大幅に削減される可能性があります。 ユーザーが SDWAN または VPN クライアントも使用している場合は、同様の追加の利点があります。 一部の組織では、一般的な方法として、より多くのデータがパブリック インターネット接続を経由することを好む場合もあります。

SDWAN または VPN の構成にも同じオプションを適用できます。 たとえば、ユーザーが SDWAN または VPN を使用してMicrosoft 365トラフィックを企業ネットワークにルーティングし、そのネットワークのプライベート拡張機能を利用してクロスボーダー混雑を回避しています。 ユーザーの SDWAN または VPN を構成して、会議や通話のリアルタイム トラフィックTeams VPN ルーティングから除外できるようになりました。 この VPN 構成は、分割トンネリングと呼ばれます。 詳細については、「[Office 365の VPN 分割トンネリング](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)」を参照してください。

また、リアルタイム トラフィックを含め、すべてのMicrosoft 365 トラフィックに対して SDWAN または VPN を引き続き使用Microsoft Teams。 Microsoft には、SDWAN または VPN ソリューションの使用に関する推奨事項はありません。

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Teams会議のホーム、モバイル、ユーザー ネットワークのベスト プラクティス

中国のユーザーは、固定電話またはモバイル接続を使用して中国のパブリック インターネット サービスに接続するだけで、これらの機能強化を利用できます。 パブリック インターネット上でリアルタイムのメディア オーディオおよびビデオ トラフィックをTeamsすると、接続と品質が向上します。

ただし、他のMicrosoft 365 サービスや、チャットやファイルなどのTeams内のその他のトラフィックからのデータは、これらの機能強化の恩恵を直接受けられません。 組織のネットワーク外のユーザーは、このトラフィックに対して引き続きネットワーク パフォーマンスが低下する可能性があります。 この記事で説明したように、VPN または SDWAN を使用してこれらの影響を軽減できます。 また、ユーザーが Web クライアントを介してリッチ デスクトップ クライアントを使用し、アプリ内キャッシュをサポートしてネットワークの問題を軽減することもできます。

### <a name="identifying-teams-real-time-media-network-traffic"></a>リアルタイム メディア ネットワーク トラフィックTeams識別する

ネットワーク デバイスまたは VPN/SDWAN のセットアップを構成するには、Teamsリアルタイムメディアオーディオトラフィックとビデオ トラフィックのみを除外する必要があります。 トラフィックの詳細は、ID 11 のOffice 365 [URL と IP アドレス範囲](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams)の公式リストにあります。 その他のすべてのネットワーク構成はそのまま残す必要があります。

Microsoft は、可能な限り広範なネットワーク アーキテクチャと特性に対するクライアントのMicrosoft 365ユーザー エクスペリエンスとパフォーマンスの向上に継続的に取り組んでいます。 [Office 365 Networking Tech Community](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)にアクセスして、会話の開始または参加、リソースの検索、機能の要求と提案の送信を行います

## <a name="related-articles"></a>関連記事

[概要: Microsoft 365の VPN 分割トンネリング](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365用の VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365の一般的な VPN 分割トンネリング シナリオ](microsoft-365-vpn-common-scenarios.md)

[VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
