---
title: 組織外部のユーザーとの共有
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
description: Teams、OneDrive、SharePoint のような Microsoft 365 アプリを組織外のユーザーと共同作業するために構成する方法について説明します。
ms.openlocfilehash: 7b8e5e30d8222d055fc5f64472c4083db614d4bd
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261515"
---
# <a name="collaborating-with-people-outside-your-organization"></a>組織外部のユーザーとの共有

Microsoft 365 の外部共有機能は、ディレクトリにアカウントを持たなかったパートナー、ベンダー、顧客、その他のユーザーと共同作業を行う機会を組織内のユーザーに提供します。 チーム全体またはサイト全体を組織外のユーザーと共有したり、個々のファイルと共有することができます。

組織外のユーザーとの共同作業は、次の 2 つの主要なコンポーネントで構成されます。

- **共有を** 有効にする - Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint 全体の共有コントロールを構成して、組織に必要な共有レベルを許可します。
- 追加のセキュリティを有効にする **-** 基本的な共有機能は組織外のユーザーに認証を要求するように構成することができますが、Microsoft 365 には、データを保護し、外部と共有しながらガバナンス ポリシーを維持するのに役立つ多くの追加のセキュリティ機能とコンプライアンス機能が提供されています。

## <a name="enable-sharing"></a>共有を有効にする

既定では、Microsoft 365 では、組織外のユーザーとの共有が有効になっています。 多くの外部共有シナリオは、それ以上の構成なしで動作します。 使用しているシナリオの設定を確認するか、新しいシナリオを有効にするには、次のオプションから選択します。

- [ドキュメントで](collaborate-on-documents.md) 共同作業を行う - Microsoft 365 を構成して、組織外のユーザー (ゲストと認証されていないユーザーの両方) とのファイルとフォルダーの共有とコラボレーションを許可する方法について説明します。
- [サイトで共同作業を行う](collaborate-in-site.md) - ゲストと SharePoint サイトを共有するために Microsoft 365 を構成する方法について説明します。
- [チームとして共同作業を行う](collaborate-as-team.md) - Teams でゲストコラボレーションを有効にするために Microsoft 365 を構成する方法について説明します。

Microsoft 365 全体で利用可能なゲスト共有設定の包括的な説明については [、Microsoft 365 ゲスト共有設定のリファレンスを参照してください](microsoft-365-guest-settings.md)。

## <a name="enable-additional-security"></a>追加のセキュリティを有効にする

組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または意図的な不適切な共有からコンテンツを保護するための追加のセーフガードを検討します。

- [認証されていないユーザーとファイル](best-practices-anonymous-sharing.md) やフォルダーを共有するためのベスト プラクティス - 認証されていないユーザーと共有するためのベスト プラクティスについて説明します。
- [偶発的な](share-limit-accidental-exposure.md) 露出を制限する - 組織外のユーザーと機密性の高いコンテンツを誤って共有する可能性を減らす方法について学習します。
- セキュリティで保護されたゲスト共有環境を作成する[-](create-secure-guest-sharing-environment.md)組織外のユーザーとの共有が安全で安全な方法で行われ、ガバナンス要件を満たしていることを確認するために Microsoft 365 で提供されるツールについて説明します。

## <a name="collaborate-with-partner-companies"></a>パートナー企業との共同作業

別の組織の多くのゲストが関与する大規模なプロジェクトに取り組む場合、またはゲストが頻繁に変更される継続的なベンダー関係がある場合は、Azure Active Directory の権利管理を使用してゲスト管理を簡素化し、パートナー企業が責任を共有できます。 詳細 [については、「管理されたゲストと B2B エクストラネットを作成する」](b2b-extranet.md) を参照してください。

## <a name="limit-sharing"></a>共有を制限する

Microsoft 365 の共有機能の一部がガバナンス ポリシーと競合する場合は [、「Microsoft 365](microsoft-365-limit-sharing.md) で共有を制限する」を参照して、共有を制限するオプションについて確認してください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのファイルコラボレーションの説明](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Microsoft 365 で SharePoint でのファイルのコラボレーションを計画する](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
