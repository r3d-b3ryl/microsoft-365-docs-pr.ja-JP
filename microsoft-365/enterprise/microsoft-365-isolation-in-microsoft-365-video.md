---
title: Office 365 ビデオ でのテナントの分離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、テナント分離が各テナントの保存されたビデオを 365 ビデオで分離Officeします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fc67b17aa40b3bca9ce6d73ebb7e18319e780339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918932"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 ビデオ でのテナントの分離

> [!NOTE]
> Office 365 ビデオは Microsoft Stream に置き換えられる。 ビデオ コラボレーションにインテリジェンスを追加する新しいエンタープライズ ビデオ サービスの詳細と、現在の Microsoft 365 ビデオのお客様の移行計画について詳しくは [、「Office 365 Video](/stream/migrate-from-office-365)transition to Microsoft Stream の概要」をご覧ください。

## <a name="introduction"></a>はじめに

Azure Storage は、365 ビデオおよび Sway Office含む複数の 365 Officeデータを格納するために使用されます。 Azure Storage には BLOB ストレージが含まれています。これは、構造化されていないデータを格納するために使用される、拡張性の高い REST ベースのクラウド オブジェクト ストアです。 Azure Storage では、単純なアクセス制御モデルを使用します。各 Azure サブスクリプションは、1 つ以上のストレージ アカウントを作成できます。 各ストレージ アカウントには、そのストレージ アカウント内のすべてのデータへのアクセスを制御するために使用される 1 つのシークレット キーがあります。 これは、ストレージがアプリケーションに関連付けられている一般的なシナリオをサポートし、それらのアプリケーションが関連付けられたデータを完全に制御できます。たとえば、Sway は Azure Storage にコンテンツを格納します。 Sway のすべての顧客コンテンツは、共有 Azure ストレージ アカウントに格納されます。 各ユーザーのコンテンツは、Azure ストレージ内の BLOB の個別のディレクトリ ツリーにあります。

顧客環境へのアクセスを管理するシステム (Azure Portal、SMAPI など) は、Microsoft が運用する Azure アプリケーション内で分離されます。 これにより、顧客アクセス インフラストラクチャと顧客アプリケーションとストレージ層が論理的に分離されます。

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 ビデオ でのテナントの分離

[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) は、組織がビデオ コンテンツを投稿、共有、および検出するための高度に安全で組織全体の宛先を組織に提供するエンタープライズ ポータルです。 Office 365 ビデオでは、各テナントのビデオは、すべての場所で分離および暗号化され、組織のビデオに対するアクセス権とアクセス許可を持つ認証済みユーザーにのみ使用できます。 Office 365 ビデオでは、次のテクノロジを組み合わせて使用します。

- SharePoint Online は、ビデオ ファイルとメタデータ (ビデオ タイトル、説明など) を格納するために使用されます。 また、セキュリティとコンプライアンス層 (認証を含む) と検索機能も提供します。
- Azure Media Services では、トランスコード、アダプティブ ストリーミング、セキュリティで保護された配信 (AES 暗号化を使用)、およびサムネイル機能が提供されます。

[Azure Media Services](https://azure.microsoft.com/services/media-services/) は、クラウドでエンドツーエンドのメディア ワークフローを有効にするための、サービスとしてのプラットフォームサービスです。 このプラットフォームは、世界中の Azure データセンターを通じてメディアのアップロード、エンコード、暗号化 (PlayReady を使用)、およびメディアの配信を行う REST API を提供します。

365 ビデオOfficeアップロードはすべて HTTPS 経由で行われます。 ビデオ ファイルがアップロードされると、SharePoint Online に保存され、ファイルのコピーが暗号化されたチャネルを介して Azure Media Services に送信されます。 Azure Media Services は、視聴エクスペリエンス (モバイル、低帯域幅、高帯域幅など) に最適化された複数の形式にビデオをトランスコードします。 これらのファイルは、アップロード時に取得された元のファイルと共に、Azure BLOB ストレージに格納されます。 ファイルは、再生に MPEG 共通暗号化パッケージ アルゴリズム (または以前の PlayReady バージョン) ごとに AES 128 を使用して暗号化され、Azure BLOB ストレージに格納される前に AES 256 ストレージ暗号化を使用して暗号化されます。 (Azure Media Services クライアント SDK を使用すると、使用する暗号化を制御できます。 たとえば、Azure Media Services ストレージ暗号化 (AES 256) を価値の高いメディア アセットに適用してから、Azure BLOB ストレージをアップロードできます)。

Azure Media Services では、ビデオのサムネイルも生成され、サムネイル メタデータと共に暗号化されたチャネルを介して SharePoint Online に送信されます。