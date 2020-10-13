---
title: Microsoft マネージド デスクトップの役割と責任
description: この記事では、microsoft マネージドデスクトップのために Microsoft によって提供される役割と責任について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8ced46ea30c7225fd3e5c8f1309ef482542e51b2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445785"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft マネージド デスクトップの役割と責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

組織が Microsoft マネージドデスクトップに登録されている場合、Microsoft は何を行いますか? 組織の責任は何ですか。

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft の役割と責任

Microsoft では、次の主要な役割と責任を提供しています。

役割または責任 | 説明
--- | ---
MDM ポリシーの管理 | Microsoft は、ベストプラクティスに従って MDM ポリシーを適用し、ポリシーの変更に対する要求を検討します。 また、 [デバイスポリシー](../service-description/device-policies.md)で規定されているように、テナントにも変更を加えます。
ユーザーサポート | Microsoft は、すべての登録ユーザーのために、Microsoft のすべての管理対象デスクトップデバイスにプレインストールされている Get Help アプリを使用して、デバイス、Windows、および Microsoft 365 アプリのためのユーザーサポートを提供します。 
Microsoft Managed Desktop service サポート | Microsoft は、Microsoft の管理されたデスクトップ運用チームを通じて、お客様の IT 部門にサポートを提供します。 このチームは、お客様の Microsoft Managed Desktop environment の技術的なトラブルシューティング、変更要求、インシデント管理をサポートします。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。
セキュリティの監視 | Microsoft は microsoft Defender ATP を使用して、microsoft の管理されたデスクトップデバイスを監視します。 Microsoft Managed デスクトップセキュリティ操作センター (SOC) が脅威を検出した場合は、お客様に通知し、デバイスを分離して、問題をリモートで修正します。 詳細については、「 [Security](../service-description/security.md)」を参照してください。
更新の監視と管理 | Microsoft マネージドデスクトップデバイスを積極的に監視して、Microsoft Windows および Microsoft Office の最新の品質と機能の更新プログラムがインストールされていることを確認しています。 詳細については、「 [更新プログラムの処理方法](../service-description/updates.md)」を参照してください。
ユーザーとデバイスのグループ化 | Microsoft Managed Desktop operations team は、IT 運用の一部として必要なデバイスとユーザーグループを作成し、管理します。 これらのグループへのメンバーシップまたは構成の変更は許可されていません。 これらのグループを変更すると、予期しないデバイス構成が発生し、機能が失われる可能性があります。 これらのグループに関する問題または質問が一度確立されると、IT 管理者は Microsoft マネージドデスクトップ操作に問い合わせることができます。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。

## <a name="your-roles-and-responsibilities"></a>自分の役割と責任

このような一般的な役割と責任のセットは展開に必要ですが、Microsoft からは提供されていません。 これは網羅的なものではありませんが、ほとんどの組織に適用されます。 自分と Microsoft の両方が責任を持ついくつかのアイテムがあります。 

役割または責任 | 説明
--- | ---
変更管理 | Microsoft は、Microsoft の管理されたデスクトップ環境に変更を加える必要がある場合に、事前にお客様に通知します。 詳細については、「 [サービスの変更と通信](../service-description/servicechanges.md)」を参照してください。<br><br>独自の変更管理プロセスを用意し、Microsoft Managed Desktop Operations team との連絡先を設定する必要があります。 また、これらの変更を確認して承認するためのリソースも必要です。 詳細については、「 [操作と監視](../service-description/operations-and-monitoring.md)」を参照してください。  
ID 管理 | ユーザーアカウントを作成し、ユーザーをグループに割り当て、メタデータを最新の状態に維持する責任があります。 
エンタープライズ構成および管理用の Microsoft 365 アプリ | Microsoft は、Office アプリケーションがユーザーに展開されることを保証する責任を担います。これらのアプリケーションは、最新の状態に保たれます。 <br><br> Microsoft 365 のサービスとポリシーを管理する責任があります (Exchange Online 管理の責任を含む)。<br>-電子メール管理<br>-メールボックスとルールの構成<br>-オンプレミスの Exchange 管理<br><br>また、Microsoft 365 管理センターで設定されているコラボレーションツール、SharePoint server 管理、ドメイン管理、およびセキュリティと情報ポリシーについても責任を担います。 
ユーザー サポート | 次のユーザーサポートを提供する必要があります。 <br>-オンサイトインフラストラクチャ: ネットワークとインターネットのすべての接続、VPN インフラストラクチャとクライアントの構成、ローカルの会議室装置、プリンター、プロキシサーバーと構成、ファイアウォール。<br><br>-企業全体にわたるクラウドリソース: 電子メール、SharePoint、コラボレーションサービス、およびその他のクラウドインフラストラクチャは、企業全体にわたるテクノロジのフットプリントに関連しています。<br><br>-基幹業務およびその他の会社固有のアプリケーション。
アプリ | 役割と責任は、Microsoft マネージドデスクトップの一部として提供されるアプリや、提供するアプリによって多少異なります。 <br><br>Microsoft によって提供されるアプリ (Microsoft 365 Apps for enterprise (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams、OneNote) は、 **microsoft** が展開、更新、およびサポートのための完全なサービスを提供します。 これらのアプリのライセンスを取得して割り当てる必要があり、セキュリティグループにユーザーを追加して、寿命を管理し、必要なアドオンを**展開する必要**があります。<br><br>提供するアプリ (基幹業務アプリなど) については、自分でパッケージ化するのか、Microsoft 以外のベンダーに依頼するのかにかかわらず、次の操作を行う **必要** があります。 <br><br>-対象ユーザーグループに必要なアプリケーションを識別する<br>-アプリ展開用の Azure AD グループの作成と管理<br>-Microsoft Intune の展開基準を満たすようにアプリをパッケージ化する<br>-Microsoft Intune へのアプリのアップロード<br>-Microsoft マネージドデスクトップ環境でのアプリのテスト<br>-ユーザーとのアプリのテスト<br>-アプリケーションに対するユーザーの管理と割り当て<br>-Microsoft Intune を使用してアプリケーションの更新プログラムを識別して展開する<br>-廃止されたアプリケーションをアンインストールおよび削除する<br>-調達および割り当てライセンス<br>-基幹業務アプリのユーザーサポートを提供する<br>-アプリの設定をリモートで管理する<br><br>**Microsoft** は、アプリケーションをリモートクライアントに配信するための microsoft Intune 展開ツールを提供します。<br><br>詳細については、「 [Apps](../get-ready/apps.md)」を参照してください。
セキュリティの監視と対応 | Microsoft が管理するデスクトップデバイスではないデバイスのインシデントを調査および解決し、そのサービスに影響を与える可能性のある問題が Microsoft Managed Desktop Operations Team に通知されるようにする責任があります。
運用のサポート | 組織内で優先する連絡先と対象の専門家の一覧を提供する必要があります。 Microsoft マネージドデスクトップとは無関係な運用インシデントの場合は、これらの機能が必要です。 <br><br>また、Microsoft Managed Desktop に含まれていないデバイスやサービスのインシデントを調査および解決し、Microsoft マネージドデスクトップ運用チームに常に通知されるようにする責任もあります。
ネットワークインフラストラクチャ (VPN を含む) | インターネット接続、ネットワーク制御、プロキシ構成、リモート接続インフラストラクチャを含む、すべてのネットワーク関連のインフラストラクチャとサービスのセットアップ、構成、および管理 (トラブルシューティングとデバッグを含む) を担当しています。<br><br>プロキシが (ハードウェアまたはソフトウェアで) 構成されている場合は、プロキシが許可する必要がある Url のコレクションがあります。 複数のプロキシによる競合または非互換性のトラブルシューティングを担当しています。 構成可能な設定を使用して、組織に固有のネットワークプロキシを追加することができます。 詳細については、「 [構成可能な設定](../working-with-managed-desktop/config-setting-ref.md#proxy)」を参照してください。<br><br>詳細については、「 [プロキシの構成](../get-ready/network.md)」を参照してください。
印刷 | プリンターと印刷キューをインストール、管理、および管理する責任があります。 クラウド印刷は推奨されるソリューションですが、必須ではありません。 




