---
title: Microsoft マネージドデスクトップの役割と責任
description: このトピックでは、microsoft が Microsoft マネージドデスクトップで提供する役割と責任について説明します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: a51738b993a8a3683769d10882877b3b42d34ddf
ms.sourcegitcommit: 7edeea1311ebb79a8c72418d2c6451b94fb788cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "35061850"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft マネージドデスクトップの役割と責任


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

組織が Microsoft マネージドデスクトップに登録されている場合、Microsoft は何を行いますか? 組織の責任は何ですか。

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft の役割と責任

Microsoft によって提供される主な役割と責任は、以下のとおりです。

役割または責任 | 説明
--- | ---
MDM ポリシーの管理 | Microsoft は、ベストプラクティスに従って MDM ポリシーを適用し、ポリシーの変更に対する要求を検討します。 また、[デバイスポリシー](../service-description/device-policies.md)で規定されているように、テナントに変更を加えます。
エンドユーザーサポート | Microsoft は、すべての登録ユーザーのために、Microsoft のすべての管理対象デスクトップデバイスにプレインストールされている Get Help アプリを使用して、デバイス、Windows、および Office 製品スイートのエンドユーザーサポートを提供します。 
Microsoft Managed Desktop service サポート | Microsoft は、Microsoft Managed Desktop Operations Team を使用して、お客様の IT 部門にサポートを提供します。 このチームは、お客様の Microsoft Managed Desktop environment の技術的なトラブルシューティング、変更要求、インシデント管理をサポートします。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。
セキュリティの監視 | Microsoft は、Windows Defender ATP を使用して、お客様の Microsoft Managed Desktop デバイスを監視します。 Microsoft Managed Desktop Security Operations Center (SOC) によって脅威が検出された場合、Microsoft はお客様に通知し、デバイスを分離して、問題をリモートで修正します。 詳細については、「 [Security](../service-description/security.md)」を参照してください。
更新の監視と管理 | Microsoft は、お客様の microsoft Managed Desktop デバイスを積極的に監視し、Microsoft Windows および Microsoft Office の最新の品質および機能の更新プログラムがインストールされていることを確認します。 詳細については、「[更新プログラムの処理方法](../service-description/updates.md)」を参照してください。
ユーザーとデバイスのグループ化 | Microsoft Managed Desktop operations team は、IT 運用の一部として必要なデバイスとユーザーグループを作成し、管理します。 これらのグループへのメンバーシップまたは構成の変更は許可されていません。 これらのグループを変更すると、予期しないデバイス構成が発生し、機能が失われる可能性があります。 これらのグループに関する問題または質問が一度確立されると、IT 管理者は Microsoft マネージドデスクトップ操作に問い合わせることができます。 詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。

## <a name="your-roles-and-responsibilities"></a>自分の役割と責任

以下は、Microsoft によって提供されていないが、正常に展開するために必要な、一般的な役割と責任のセットの追加です。 これは網羅的なものではありませんが、ほとんどの組織に適用されます。 Microsoft とお客様との共有 responsibilties の両方について、以下にいくつかの項目があります。 

役割または責任 | 説明
--- | ---
変更管理 | Microsoft は、Microsoft の管理されたデスクトップ環境に変更を加える必要がある場合に、事前にお客様に通知します。 お客様には、独自の変更管理プロセスを用意し、Microsoft の管理されたデスクトップ運用チームで担当の連絡先を設定する必要があります。 お客様は、これらの変更を確認して承認するためのリソースも必要です。 詳細については、「[操作と監視](../service-description/operations-and-monitoring.md)」を参照してください。  
ID 管理 | お客様は、ユーザーアカウントを作成し、ユーザーをグループに割り当て、メタデータを最新の状態に維持する責任があります。 
Office 365 の構成と管理 | Microsoft は、Office アプリケーションがエンドユーザーに展開されることを保証する責任を担います。これらのアプリケーションは、最新の状態に保たれます。 <br><br> お客様は、Exchange Online 管理の責任を含む Office 365 のサービスとポリシーを管理する責任があります。<br>-電子メール管理<br>-メールボックスとルールの構成<br>-オンプレミスの Exchange 管理<br><br>お客様は、Office 365 管理ポータルで設定されているコラボレーションツール、SharePoint server 管理、ドメイン管理、セキュリティおよび情報ポリシーにも責任を担います。 
エンドユーザーサポート | お客様は、以下のことをエンドユーザーにサポートする責任を負います。 <br>-サイトインフラストラクチャ: ネットワークとインターネットのすべての接続、VPN インフラストラクチャとクライアントの構成、ローカルの会議室装置、プリンター、プロキシサーバーと構成、ファイアウォール。<br><br>-企業全体にわたるクラウドリソース: 電子メール、SharePoint、コラボレーションサービス、およびその他のクラウドインフラストラクチャは、企業全体にわたるテクノロジのフットプリントに関連しています。<br><br>-基幹業務およびその他の会社固有のアプリケーション。
アプリ | 役割と責任は、Microsoft マネージドデスクトップの一部として提供されているアプリと、提供するアプリによって多少異なります。 <br><br>Microsoft が提供するアプリ (Office 365 ProPlus Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、Teams、OneNote) は、 **microsoft**が展開、更新、およびサポートのための完全なサービスを提供する予定です。 **** これらのアプリのライセンスを取得して割り当てる必要があり、セキュリティグループにユーザーを追加し、ライフサイクルを管理して、必要な Office 365 のアドオンを展開する必要があります。<br><br>提供するアプリ (基幹業務アプリなど) については、自分でパッケージ化するのか、Microsoft 以外のベンダーに依頼するのかにかかわらず、次の操作を行う**必要**があります。 <br><br>-対象ユーザーグループに必要なアプリケーションを識別する<br>-アプリ展開用の Azure AD グループの作成と管理<br>-Microsoft Intune の展開基準を満たすようにアプリをパッケージ化する<br>-Microsoft Intune へのアプリのアップロード<br>-Microsoft マネージドデスクトップ環境でのアプリのテスト<br>-エンドユーザーによるアプリのテスト<br>-アプリケーションに対するユーザーの管理と割り当て<br>-Microsoft Intune を使用してアプリケーションの更新プログラムを識別して展開する<br>-廃止されたアプリケーションをアンインストールおよび削除する<br>-調達および割り当てライセンス<br>-基幹業務アプリのエンドユーザーサポートを提供する<br>-アプリの設定をリモートで管理する<br><br>**Microsoft**は、アプリケーションをリモートクライアントに配信するための microsoft Intune 展開ツールを提供します。<br><br>詳細については、「[アプリ](../get-ready/apps.md)」を参照してください。
セキュリティの監視と応答 | お客様は、Microsoft が管理していないデスクトップデバイスのインシデントを調査および解決し、そのサービスに影響を与える可能性のある問題があるかどうかを Microsoft Managed Desktop Operations Team に通知する責任を負います。
運用のサポート | お客様は、お客様に推奨されるお客様の連絡先と該当分野の専門家のリストを提供する責任を担います。 Microsoft では、管理されていないデスクトップの運用インシデントがある場合には、これらの機能が必要です。 <br><br>お客様は、Microsoft が管理していないデスクトップデバイスおよびサービスのインシデントを調査および解決し、Microsoft の管理対象デスクトップ運用チームに常に通知されるようにする責任もあります。
ネットワークインフラストラクチャ (VPN を含む) | お客様は、インターネット接続、ネットワーク制御、プロキシ構成、およびリモートを含む、すべてのネットワーク関連のインフラストラクチャとサービスのセットアップ、構成、および管理 (トラブルシューティングおよびデバッグ) を担当しています。接続インフラストラクチャ。<br><br>プロキシが (ハードウェアまたはソフトウェアで) 構成されている場合は、プロキシが許可する必要がある Url のコレクションがあります。 お客様は、複数のプロキシによって競合または非互換性のトラブルシューティングを行う必要があります。 構成可能な設定を使用して、組織に固有のネットワークプロキシを追加することができます。 詳細については、「[構成可能な設定](../working-with-managed-desktop/config-setting-ref.md#proxy)」を参照してください。<br><br>詳細については、「[プロキシの構成](../get-ready/network.md)」を参照してください。
印刷 | お客様は、プリンターおよび印刷キューをインストール、管理、および管理する責任があります。 クラウド印刷は推奨されるソリューションですが、必須ではありません。 




