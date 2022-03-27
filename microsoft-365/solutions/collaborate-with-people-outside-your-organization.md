---
title: 組織外のユーザーとの共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 組織外のユーザーと共同作業をするために、Teams、OneDrive、SharePoint など、Microsoft 365 アプリを構成する方法について説明します。
ms.openlocfilehash: 65511cbafdc1f5a666c11e1bef7fefd6e6852ee3
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712776"
---
# <a name="collaborating-with-people-outside-your-organization"></a>組織外のユーザーとの共同作業

Microsoft 365 の外部共有機能により、組織内のユーザーはディレクトリにアカウントを持たないパートナー、ベンダー、顧客などと共同作業ができます。 チーム、チャネル、またはサイト全体を組織外のユーザーと共有したり、個々のファイルを共有することができます。

組織外のユーザーとの共同作業は、次の主要なコンポーネントで構成されます。

- **共有を有効にする** - Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint 全体で共有コントロールを構成して、組織に必要な共有レベルを許可します。
- **組織の関係を構成** する - 共有チャネルを使用している場合は、Azure Active Directory でテナント間アクセス設定を構成して、共同作業を行う組織ごとに B2B 直接接続アクセスを許可する必要があります。 (これらの組織では、テナントとの組織関係も構成する必要があります)。
- **追加のセキュリティを有効にする** - 組織外のユーザーに認証を要求するように基本的な共有機能を構成することができると同時に、Microsoft 365 には、データを保護し、外部と共有しながらガバナンス ポリシーを維持するのに役立つ多くの追加のセキュリティとコンプライアンス機能があります。

外部[共有がコラボレーション](/microsoft-365/solutions/setup-secure-collaboration-with-teams) ガイダンス全体とどのように結びMicrosoft 365、Microsoft Teamsグループとの安全なコラボレーションのセットアップを参照Microsoft 365参照してください。

## <a name="enable-sharing"></a>共有を有効にする

既定では、ゲスト アクセスまたは匿名アクセスを使用して組織外のユーザーとの共有が有効になっていますが、共有チャネルは、Azure AD で組織の関係を構成して有効にする必要があります。 ほとんどのゲスト共有シナリオは、それ以上の構成なしで動作します。 使用しているシナリオの設定を確認するか、新しいシナリオを有効にするには、次のオプションから選びます。

- [ドキュメントの共同作業](collaborate-on-documents.md) - 組織外のユーザー (ゲストと認証されていないユーザーの両方) とファイルやフォルダーを共有および共同作業を許可するように Microsoft 365 を構成する方法について説明します。
- [サイトでの共同作業](collaborate-in-site.md) - ゲストとの SharePoint サイトの共有を有効にするために Microsoft 365 を構成する方法について説明します。
- [チームとして共同作業](collaborate-as-team.md) - Teams でゲスト コラボレーションを有効にするために Microsoft 365 を構成する方法について説明します。
- [チャネル内の外部参加者と共同作業](/microsoft-365/solutions/collaborate-teams-direct-connect) を行い、共有チャネルで組織外のユーザーと共同作業を行います。

Microsoft 365 で利用できるゲスト共有設定の全体像については、「[Microsoft 365 ゲスト共有設定リファレンス」](microsoft-365-guest-settings.md) をご参照ください。

## <a name="enable-additional-security"></a>追加のセキュリティを有効にする

組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または意図的な不適切な共有からコンテンツを保護するために追加の安全対策を検討します。

- [認証されていないユーザーとファイルとフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md) - 非認証ユーザーと共有するためのベスト プラクティスについて説明します。
- [偶発的な露出を制限する](share-limit-accidental-exposure.md) - 組織外のユーザーと機密性の高いコンテンツを誤って共有する可能性を減らす方法について説明します。
- [セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md) -組織外のユーザーとの共有が安全かつセキュリティで保護された方法で行われ、ガバナンス要件を満たしていることを確認するために Microsoft 365 で提供されるツールについて説明します。

## <a name="collaborate-with-partner-companies"></a>パートナー企業と共同作業する

別の組織のゲストを含む大規模なプロジェクトに取り組む場合は、共有チャネルを検討してください。 共有チャネルはゲスト アカウントを使用しないので、他の組織のユーザーは、組織に個別にログインすることなく、共有チャネルに直接アクセスできます。

ゲストが頻繁に変更される継続的なベンダー関係がある場合は、Azure Active Directory でエンタイトルメント管理を使用してゲスト管理を簡素化し、パートナー企業が責任を共有できます。 詳細については、「[Create a B2B extranet with managed guests (管理されたゲストで B2B エクストラネットを作成する)](b2b-extranet.md)」を参照してください。

## <a name="limit-sharing"></a>共有を制限する

Microsoft 365 の共有機能の一部がガバナンス ポリシーと競合する場合、共有を制限するオプションについては、「 [Microsoft 365で共有を制限する](microsoft-365-limit-sharing.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのファイル共同作業の概要](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 を使用して SharePoint のファイルの共同作業を計画する](/sharepoint/deploy-file-collaboration)
