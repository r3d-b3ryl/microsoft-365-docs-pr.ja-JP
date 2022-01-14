---
title: Microsoft マネージド デスクトップの役割と責任
description: この記事では、Microsoft for Microsoft Managed Desktop が提供する役割と責任について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 2a9a1d4314503b900d774851b2d23587d4c37579
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034451"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft マネージド デスクトップの役割と責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

組織が Microsoft Managed Desktop に登録されている場合、Microsoft は何をしますか? 組織の責任は何ですか?

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft の役割と責任

Microsoft は、次の主要な役割と責任を提供します。

役割または責任 | 説明
--- | ---
MDM ポリシーの管理 | Microsoft は、ベスト プラクティスに従って MDM ポリシーを適用し、ポリシー変更の要求を検討します。 また、[デバイス ポリシー] に規定されているテナントにも変更 [を加えます](../service-description/device-policies.md)。
ユーザー サポート | デバイスへのアクセスを昇格し、必要に応じてサポート要求を介してエスカレートする問題のメカニズムを提供します。 詳細については、「ユーザー サポート」 [を参照してください](../service-description/user-support.md)。
Microsoft Managed Desktop サービスのサポート | Microsoft は、Microsoft Managed Desktop Operations Team を通じて IT 部門にサポートを提供します。 このチームは、お客様の Microsoft Managed Desktop 環境の技術的なトラブルシューティング、変更要求、インシデント管理をサポートします。 詳細については [、「Microsoft Managed Desktop の管理サポート」を参照してください](../working-with-managed-desktop/admin-support.md)。
セキュリティ監視 | Microsoft は、Microsoft Defender for Endpoint を使用して Microsoft Managed Desktop デバイスを監視します。 Microsoft Managed Desktop Security Operations Center (SOC) が脅威を検出した場合、お客様に通知し、デバイスを分離し、リモートで問題を修正します。 詳細については [、「Security」を参照してください](../service-description/security.md)。
監視と管理を更新する | Microsoft Managed Desktop デバイスを積極的に監視し、最新の品質と機能の更新プログラムが Microsoft Windows および Microsoft Office。 詳細については、「更新プログラムの [処理方法」を参照してください](../service-description/updates.md)。
ユーザーとデバイスのグループ化 | Microsoft Managed Desktop の運用チームは、IT 操作の一環として、必要なデバイスグループとユーザー グループを作成および管理します。 これらのグループには、メンバーシップや構成の変更は許可されません。 これらのグループを変更すると、デバイスの予期しない構成や機能の喪失につながる可能性があります。 これらのグループに関する問題や質問が確立されると、IT 管理者は Microsoft Managed Desktop の操作に問い合わせできます。 詳細については [、「Microsoft Managed Desktop の管理サポート」を参照してください](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>役割と責任

この一般的な役割と責任のセットは展開に必要ですが、Microsoft によって提供されるのではありません。 これは網羅的ではありませんが、ほとんどの組織に適用されます。 ユーザーと Microsoft の両方が責任を共有する項目がいくつかある。 

役割または責任 | 説明
--- | ---
変更管理 | Microsoft は、Microsoft Managed Desktop 環境に変更を加える必要がある場合は、事前にお客様に通知します。 詳細については、「サービスの変更 [と通信」を参照してください](../service-description/servicechanges.md)。<br><br>独自の変更管理プロセスを持ち、Microsoft Managed Desktop Operations チームと連絡先を確立している必要があります。 また、これらの変更を確認および承認するリソースも必要です。 詳細については、「操作と監視 [」を参照してください](../service-description/operations-and-monitoring.md)。  
ID 管理 | ユーザー アカウントを作成し、ユーザーをグループに割り当て、メタデータを最新の状態に保つ責任があります。 
Microsoft 365 Apps for enterpriseと管理 | Microsoft は、ユーザーにOfficeし、それらのアプリケーションを最新の状態に保つ必要があります。 <br><br> 管理責任を含む、Microsoft 365ポリシーを管理するExchange Online責任があります。<br>- メールの管理<br>- メールボックスとルールの構成<br>- Exchangeオンプレミス管理<br><br>また、コラボレーション ツール、SharePoint管理、ドメイン管理、セキュリティおよび情報ポリシーを管理する必要があります。Microsoft 365 管理センター。 
ユーザー サポート | お客様または指定されたサポート パートナーを通じて、最初の連絡先から解決まで、すべてのユーザー サポートと技術サポートをユーザーに提供します。 ユーザー サポートを直接提供するか、パートナーと一緒にこれらの分野のサポートを提供する必要があります。 <br><br>- オンサイト インフラストラクチャ: すべてのネットワークとインターネット接続、VPN インフラストラクチャとクライアント構成、ローカル会議室機器、プリンター、プロキシ サーバーと構成、ファイアウォール。<br><br>- 会社全体のクラウド リソース:電子メール、SharePoint、コラボレーション サービス、および会社全体のテクノロジフットプリントに関連するその他のクラウド インフラストラクチャ。<br><br>- Line of business および他の会社固有のアプリケーション。
アプリ | 役割と責任は、Microsoft Managed Desktop の一部として提供されるアプリと、提供するアプリによって多少異なります。 <br><br>Microsoft によって提供されるアプリ (Microsoft 365 Apps for enterprise Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams、および **OneNote)、Microsoft は** 展開、更新、およびサポートのフル サービスを提供します。 **これらの** アプリのライセンスを取得して割り当て、セキュリティ グループにユーザーを追加し、終末を管理し、必要なアドオンを展開する必要があります。<br><br>提供するアプリ (業務用アプリなど) の場合は、自分でパッケージ化するか、Microsoft 以外のベンダーに参加するかに関係無く、次の操作を行う必要があります。 <br><br>- 対象ユーザー グループに必要なアプリケーションの識別<br>- アプリの展開Azure ADグループの作成と管理<br>- アプリケーションをパッケージ化して、Microsoft Intune標準を満たします<br>- アプリをアプリにアップロードMicrosoft Intune<br>- Microsoft Managed Desktop 環境でのアプリのテスト<br>- ユーザーとアプリをテストする<br>- アプリケーションへのユーザーの管理と割り当て<br>- アプリケーションの更新プログラムを特定して展開するには、Microsoft Intune<br>- アプリケーションが廃止された場合のアンインストールと削除<br>- ライセンスの調達と割り当て<br>- Line-of-business アプリのユーザー サポートを提供する<br>- アプリ設定をリモートで管理する<br><br>**Microsoft** は、リモート Microsoft Intuneにアプリケーションを配信するための新しい展開ツールを提供します。<br><br>詳細については、「Apps」を [参照してください](../get-ready/apps.md)。
セキュリティの監視と対応 | Microsoft Managed Desktop デバイスではないデバイスのインシデントを調査および解決し、サービスに影響を与える可能性がある問題について Microsoft Managed Desktop Operations チームに通知を受け取る責任があります。
操作のサポート | 組織内の優先連絡先と件名の専門家の一覧を指定する必要があります。 Microsoft Managed Desktop とは無関係の運用上のインシデントがある場合は、これらの連絡先が必要です。 <br><br>また、Microsoft Managed Desktop に属していないデバイスやサービスのインシデントを調査および解決し、Microsoft Managed Desktop Operations Team に常に通知を受け取る責任があります。
VPN を含むネットワーク インフラストラクチャ | インターネット接続、ネットワーク制御、プロキシ構成、リモート接続インフラストラクチャなど、ネットワーク関連のすべてのインフラストラクチャとサービスのセットアップ、構成、管理 (トラブルシューティングとデバッグを含む) を担当します。<br><br>プロキシが (ハードウェアまたはソフトウェアで) 構成されている場合は、プロキシで許可する必要がある URL のコレクションがあります。 複数のプロキシによる競合や非互換性のトラブルシューティングは、お客様の責任で行います。 構成可能な設定を使用して、組織固有のネットワーク プロキシを追加できます。 詳細については、「構成可能な設定 [」を参照してください](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>詳細については、「プロキシ構成 [」を参照してください](../get-ready/network.md)。
印刷 | プリンターと印刷キューのインストール、保守、管理を行う責任があります。 クラウド印刷は推奨されるソリューションですが、必須ではありません。 




