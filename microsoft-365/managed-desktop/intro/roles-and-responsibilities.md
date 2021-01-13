---
title: Microsoft マネージド デスクトップの役割と責任
description: この記事では、Microsoft マネージド デスクトップ向け Microsoft が提供する役割と責任について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841317"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft マネージド デスクトップの役割と責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

組織が Microsoft マネージド デスクトップに登録されている場合、Microsoft は何をしますか? 組織の責任は何ですか?

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft の役割と責任

Microsoft は、次の重要な役割と責任を提供します。

役割または責任 | 説明
--- | ---
MDM ポリシーの管理 | Microsoft は、ベスト プラクティスに従って MDM ポリシーを適用し、ポリシー変更の要求を検討します。 また、デバイス ポリシーに規定されている方法でテナントを [変更します](../service-description/device-policies.md)。
ユーザー サポート | Microsoft では、すべての Microsoft マネージド デスクトップ デバイスにプレインストールされているヘルプ アプリを通じて、登録しているすべてのユーザー向けデバイス、Windows、および Microsoft 365 Apps for enterprise 製品スイートのユーザー サポートを提供します。 
Microsoft マネージド デスクトップ サービスのサポート | Microsoft は、Microsoft マネージド デスクトップ 運用チームを通じて IT 部門にサポートを提供します。 このチームは、お客様の Microsoft マネージド デスクトップ環境の技術的なトラブルシューティング、変更要求、インシデント管理をサポートします。 詳細については、「Microsoft マネージド デスクトップ [の管理者サポート」を参照してください](../working-with-managed-desktop/admin-support.md)。
セキュリティ監視 | Microsoft は、Microsoft Defender for Endpoint を使用して Microsoft マネージド デスクトップ デバイスを監視します。 Microsoft マネージド デスクトップ セキュリティ オペレーション センター (SOC) が脅威を検出した場合、マイクロソフトはユーザーに通知し、デバイスを分離して、問題をリモートで修正します。 詳細については、「セキュリティ」を [参照してください](../service-description/security.md)。
監視と管理を更新する | Microsoft マネージド デスクトップ デバイスを積極的に監視し、最新の品質更新プログラムと機能更新プログラムが Microsoft Windows および Microsoft Office 用にインストールされていることを確認します。 詳細については、「更新プログラムの [処理方法」を参照してください](../service-description/updates.md)。
ユーザーとデバイスのグループ化 | Microsoft マネージド デスクトップ運用チームは、IT 運用の一環として、必要なデバイスおよびユーザー グループを作成および管理します。 これらのグループに対するメンバーシップまたは構成の変更は許可されません。 これらのグループを変更すると、デバイスの予期しない構成や機能の喪失につながる可能性があります。 これらのグループに関する問題や質問が確立されると、IT 管理者は Microsoft マネージド デスクトップの操作に問い合わせできます。 詳細については、「Microsoft マネージド デスクトップ [の管理者サポート」を参照してください](../working-with-managed-desktop/admin-support.md)。

## <a name="your-roles-and-responsibilities"></a>自分の役割と責任

この一連の一般的な役割と責任は展開に必要ですが、Microsoft によって提供されるのではありません。 完全には適用できませんが、ほとんどの組織に適用されます。 お客様と Microsoft の両方が責任を共有する項目がいくつかある。 

役割または責任 | 説明
--- | ---
変更管理 | Microsoft は、Microsoft マネージド デスクトップ環境に変更を加える必要がある場合、事前にお客様に通知します。 詳細については、「サービスの変更 [と通信」を参照してください](../service-description/servicechanges.md)。<br><br>独自の変更管理プロセスが必要であり、Microsoft マネージド デスクトップ操作チームとの連絡先を確立する必要があります。 また、これらの変更を確認および承認するリソースも必要です。 詳細については、「操作と監視 [」を参照してください](../service-description/operations-and-monitoring.md)。  
ID 管理 | ユーザー アカウントを作成し、ユーザーをグループに割り当て、メタデータを最新の状態に保つ必要があります。 
Microsoft 365 Apps for enterprise の構成と管理 | Microsoft は、ユーザーにOfficeアプリケーションを確実に展開し、それらのアプリケーションを最新の状態に保つ責任を負います。 <br><br> Exchange Online の管理責任を含む、Microsoft 365 のサービスとポリシーを管理する責任があります。<br>- 電子メールの管理<br>- メールボックスとルールの構成<br>- Exchange オンプレミス管理<br><br>また、Microsoft 365 管理センターで設定されているコラボレーション ツール、SharePoint サーバー管理、ドメイン管理、セキュリティおよび情報ポリシーも担当します。 
ユーザー サポート | 次のユーザー サポートを提供する必要があります。 <br>- オンサイト インフラストラクチャ: すべてのネットワークとインターネット接続、VPN インフラストラクチャとクライアント構成、ローカル会議室機器、プリンター、プロキシ サーバーと構成、ファイアウォール。<br><br>- 会社全体のクラウド リソース: 電子メール、SharePoint、コラボレーション サービス、および会社全体のテクノロジフットプリントに関連するその他のクラウド インフラストラクチャ。<br><br>- Line of business and any other company-specific applications.
アプリ | ロールと責任は、Microsoft マネージド デスクトップの一部として提供されるアプリと提供するアプリでは多少異なります。 <br><br>Microsoft が提供するアプリ (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams、OneNote で構成される Microsoft 365 Apps for enterprise) の場合 **、Microsoft** は展開、更新、サポートのための完全なサービスを提供します。 **これらの** アプリのライセンスを取得して割り当て、セキュリティ グループにユーザーを追加し、終末を管理し、必要なアドオンを展開する必要があります。<br><br>提供するアプリ (line-of-business アプリなど) の場合は、自分でパッケージ化する場合も、Microsoft 以外のベンダーに関与する場合でも、次の操作を行う必要があります。 <br><br>- 対象ユーザー グループに必要なアプリケーションを特定する<br>- アプリ展開用の Azure ADグループの作成と管理<br>- Microsoft Intune の展開基準を満たすアプリのパッケージ化<br>- Microsoft Intune へのアプリのアップロード<br>- Microsoft マネージド デスクトップ環境でのアプリのテスト<br>- ユーザーと一緒にアプリをテストする<br>- ユーザーを管理し、アプリケーションに割り当てる<br>- Microsoft Intune を使用してアプリケーション更新プログラムを特定して展開する<br>- アプリケーションの廃止時のアンインストールと削除<br>- ライセンスの調達と割り当て<br>- 業務アプリのユーザー サポートの提供<br>- アプリ設定をリモートで管理する<br><br>**Microsoft** は、リモート クライアントにアプリケーションを配信するための Microsoft Intune 展開ツールを提供します。<br><br>詳しくは、「アプリ」をご [覧ください](../get-ready/apps.md)。
セキュリティの監視と対応 | Microsoft マネージド デスクトップ デバイスではないデバイスのインシデントを調査および解決し、サービスに影響を与える可能性がある問題について Microsoft マネージド デスクトップ運用チームに通知する責任があります。
運用サポート | 組織内の優先連絡先と対象分野の専門家の一覧を提供する必要があります。 Microsoft マネージド デスクトップとは無関係の運用インシデントが発生した場合は、これらの連絡先が必要です。 <br><br>また、Microsoft マネージド デスクトップにはないデバイスやサービスに関するインシデントを調査および解決し、Microsoft マネージド デスクトップ運用チームに常に通知する責任もあります。
VPN を含むネットワーク インフラストラクチャ | インターネット接続、ネットワーク制御、プロキシ構成、リモート接続インフラストラクチャなど、ネットワーク関連のすべてのインフラストラクチャとサービスのセットアップ、構成、管理 (トラブルシューティングとデバッグを含む) を担当します。<br><br>プロキシが (ハードウェアまたはソフトウェアで) 構成されている場合は、プロキシで許可する必要がある URL のコレクションがあります。 複数のプロキシによる競合や互換性の問題のトラブルシューティングを行う必要があります。 構成可能な設定を使用して、組織に固有のネットワーク プロキシを追加できます。 詳細については、「構成可能な設定 [」を参照してください](../working-with-managed-desktop/config-setting-ref.md#proxy)。<br><br>詳細については、「プロキシ構成」 [を参照してください](../get-ready/network.md)。
印刷 | プリンターと印刷キューをインストール、保守、管理する必要があります。 クラウド印刷は推奨されるソリューションですが、必須ではありません。 




