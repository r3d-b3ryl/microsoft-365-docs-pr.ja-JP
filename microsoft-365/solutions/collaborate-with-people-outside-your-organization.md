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
description: 組織外のユーザーとの共同作業のために、Teams、OneDrive、SharePoint などの Microsoft 365 アプリを構成する方法について説明します。
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613456"
---
# <a name="collaborating-with-people-outside-your-organization"></a>組織外のユーザーとの共同作業

Microsoft 365 の外部共有機能を使用すると、組織内のユーザーが、自分のディレクトリにアカウントを持っていないパートナー、ベンダー、顧客、および他のユーザーと共同作業を行う機会を得ることができます。 組織外のユーザーや個別のファイルに対して、チームまたはサイト全体を共有することができます。

組織外のユーザーとの共同作業は、次の2つの主要コンポーネントで構成されます。

- **共有を有効** にする-Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint の間で共有コントロールを構成して、組織で必要とされるレベルの共有を許可します。
- **追加のセキュリティを有効** にします。組織外のユーザーによる認証を要求するように基本の共有機能を構成することはできますが、Microsoft 365 には、データを保護し、外部共有している間にガバナンスポリシーを維持するために役立つ、多くの追加のセキュリティおよびコンプライアンス機能が用意されています。

## <a name="enable-sharing"></a>共有を有効にする

Microsoft 365 では、既定では、組織外のユーザーとの共有は SharePoint と OneDrive で有効になっていますが、Teams では無効になっています。 SharePoint および OneDrive の外部共有シナリオの多くは、それ以上の構成を行わなくても動作します。 使用しているシナリオの設定を確認するか、または新しいシナリオを有効にするには、次のオプションのいずれかを選択します。

- [ドキュメントに対して共同作業](collaborate-on-documents.md) を行う: Microsoft 365 を構成して、ファイルとフォルダーの組織外のユーザー (ゲストと認証されていないユーザーの両方) との共有と共同作業を可能にする方法について説明します。
- [サイトでの共同作業](collaborate-in-site.md) -ゲストを使用した SharePoint サイトの共有を有効にするように Microsoft 365 を構成する方法について説明します。
- [チームとしての共同作業](collaborate-as-team.md) -Teams でゲストコラボレーションを有効にするように Microsoft 365 を構成する方法について説明します。

Microsoft 365 で使用可能なゲスト共有設定の包括的な説明については、「 [microsoft 365 ゲスト共有設定のリファレンス](microsoft-365-guest-settings.md)」を参照してください。

## <a name="enable-additional-security"></a>追加のセキュリティを有効にする

組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または故意に不適切な共有からコンテンツを保護するための追加の保護機能を検討します。

- 認証されていない[ユーザーとファイルやフォルダーを共有するためのベストプラクティス](best-practices-anonymous-sharing.md)-認証されていないユーザーとの共有のベストプラクティスについて説明します。
- [偶発的な公開を制限](share-limit-accidental-exposure.md) する: 機密コンテンツを誤って組織外のユーザーと共有する危険性を軽減する方法について説明します。
- [セキュリティで保護されたゲスト共有環境を作成](create-secure-guest-sharing-environment.md) する-組織外のユーザーとの共有が安全かつ安全な方法で行われ、ガバナンス要件を満たしていることを確認するために、Microsoft 365 で提供されるツールについて説明します。

## <a name="collaborate-with-partner-companies"></a>パートナー企業との共同作業

他の組織から多数のゲストが関係する大規模なプロジェクトで作業している場合や、ゲストが頻繁に変更される可能性のある継続的なベンダーの関係がある場合は、Azure Active Directory の資格管理を使用して、ゲスト管理を簡略化し、パートナー会社がその責任で共有できるようにすることができます。 詳細について [は、「管理されたゲストでの B2B エクストラネットの作成](b2b-extranet.md) 」を参照してください。

## <a name="limit-sharing"></a>共有を制限する

Microsoft 365 の共有機能の一部がガバナンスポリシーと競合している場合は、「 [365 microsoft の](microsoft-365-limit-sharing.md) 共有を制限する」を参照して、共有の制限のオプションについて確認してください。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのファイルの共同作業の概要](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[Microsoft 365 を使用して SharePoint でファイルのコラボレーションを計画する](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
