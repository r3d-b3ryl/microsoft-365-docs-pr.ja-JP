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
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: 組織外のユーザーと共同作業をするために、Teams、OneDrive、SharePoint など、Microsoft 365 アプリを構成する方法について説明します。
ms.openlocfilehash: 291a5e6d75ac1b1a12a2403a9aeece9cb658afd0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213194"
---
# <a name="collaborating-with-people-outside-your-organization"></a>組織外のユーザーとの共同作業

Microsoft 365 の外部共有機能により、組織内のユーザーはディレクトリにアカウントを持たないパートナー、ベンダー、顧客などと共同作業ができます。 チームやサイト全体または単に個人的なファイルを組織外のユーザーと共有できます。

組織外のユーザーとの共同作業には、次の 2 つの主要なコンポーネントがあります。

- **共有を有効にする** - Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint 全体で共有コントロールを構成して、組織に必要な共有レベルを許可します。
- **追加のセキュリティを有効にする** - 組織外のユーザーに認証を要求するように基本的な共有機能を構成することができると同時に、Microsoft 365 には、データを保護し、外部と共有しながらガバナンス ポリシーを維持するのに役立つ多くの追加のセキュリティとコンプライアンス機能があります。

外部[共有がコラボレーション](/microsoft-365/solutions/setup-secure-collaboration-with-teams)ガイダンス全体とどのように結びMicrosoft 365、Microsoft Teamsとセキュリティで保護されたコラボレーションをセットアップするMicrosoft 365参照してください。

## <a name="enable-sharing"></a>共有を有効にする

Microsoft 365では規定で、組織外のユーザーとの共有が有効になっています。 多くの外部共有シナリオは、追加の構成なしでも動作します。 使用しているシナリオの設定を確認するか、新しいシナリオを有効にするには、次のオプションから選びます。

- [ドキュメントの共同作業](collaborate-on-documents.md) - 組織外のユーザー (ゲストと認証されていないユーザーの両方) とファイルやフォルダーを共有および共同作業を許可するように Microsoft 365 を構成する方法について説明します。
- [サイトでの共同作業](collaborate-in-site.md) - ゲストとの SharePoint サイトの共有を有効にするために Microsoft 365 を構成する方法について説明します。
- [チームとして共同作業](collaborate-as-team.md) - Teams でゲスト コラボレーションを有効にするために Microsoft 365 を構成する方法について説明します。

Microsoft 365 で利用できるゲスト共有設定の全体像については、「[Microsoft 365 ゲスト共有設定リファレンス」](microsoft-365-guest-settings.md) をご参照ください。

## <a name="enable-additional-security"></a>追加のセキュリティを有効にする

組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または意図的な不適切な共有からコンテンツを保護するために追加の安全対策を検討します。

- [認証されていないユーザーとファイルとフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md) - 非認証ユーザーと共有するためのベスト プラクティスについて説明します。
- [偶発的な露出を制限する](share-limit-accidental-exposure.md) - 組織外のユーザーと機密性の高いコンテンツを誤って共有する可能性を減らす方法について説明します。
- [セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md) -組織外のユーザーとの共有が安全かつセキュリティで保護された方法で行われ、ガバナンス要件を満たしていることを確認するために Microsoft 365 で提供されるツールについて説明します。

## <a name="collaborate-with-partner-companies"></a>パートナー企業と共同作業する

別の組織の多くのゲストが関与する大規模なプロジェクトに取り組む場合、またはゲストが頻繁に変更される継続的なベンダー 関係がある場合は、Azure Active Directory の権利管理を使用してゲスト管理を簡素化し、パートナー企業が共同責任を持つようにすることができます。 詳細については、「[Create a B2B extranet with managed guests (管理されたゲストで B2B エクストラネットを作成する)](b2b-extranet.md)」を参照してください。

## <a name="limit-sharing"></a>共有を制限する

Microsoft 365 の共有機能の一部がガバナンス ポリシーと競合する場合、共有を制限するオプションについては、「 [Microsoft 365で共有を制限する](microsoft-365-limit-sharing.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのファイル共同作業の概要](/sharepoint/intro-to-file-collaboration)

[Microsoft 365 を使用して SharePoint のファイルの共同作業を計画する](/sharepoint/deploy-file-collaboration)
