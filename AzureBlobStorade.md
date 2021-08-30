

# Azure Blob Storage


# Overview

Azure Blob storage is Microsoft's object storage solution for the cloud. Blob storage is optimized for storing massive amounts of unstructured data.

Users or client applications can access objects in Blob storage via HTTP/HTTPS, from anywhere in the world. Objects in Blob storage are accessible via the Azure Storage REST API, Azure PowerShell, Azure CLI, or an Azure Storage client library. Client libraries are available for different languages, including:

Azure Blob Storageは、Microsoftのクラウド向けオブジェクトストレージソリューションです。 BLOBストレージは、大量の非構造化データを格納するために最適化されています。

ユーザーまたはクライアントアプリケーションは、世界中のどこからでも、HTTP / HTTPSを介してBlobストレージ内のオブジェクトにアクセスできます。 Blobストレージ内のオブジェクトには、Azure Storage REST API、Azure PowerShell、Azure CLI、またはAzureStorageクライアントライブラリを介してアクセスできます。クライアントライブラリは、次のようなさまざまな言語で利用できます。



* [.NET](https://docs.microsoft.com/en-us/dotnet/api/overview/azure/storage)
* [Java](https://docs.microsoft.com/en-us/java/api/overview/azure/storage)
* [Node.js](https://github.com/Azure/azure-sdk-for-js/tree/master/sdk/storage)
* [Python](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-python)
* [Go](https://github.com/azure/azure-storage-blob-go/)
* [PHP](https://azure.github.io/azure-storage-php/)
* [Ruby](https://azure.github.io/azure-storage-ruby)

Ref : [https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blobs-overview) 


## Blob service REST API

The REST API for the Blob service defines HTTP operations against the storage account, containers, and blobs. The API includes the operations listed in the following table.

BlobサービスのRESTAPIは、ストレージアカウント、コンテナー、およびBLOBに対するHTTP操作を定義します。 APIには、次の表にリストされている操作が含

Ref : [https://docs.microsoft.com/en-us/rest/api/storageservices/blob-service-rest-api](https://docs.microsoft.com/en-us/rest/api/storageservices/blob-service-rest-api)


<table>
  <tr>
   <td><strong>手術</strong>
   </td>
   <td><strong>リソースタイプ</strong>
   </td>
   <td><strong>説明</strong>
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/list-containers2?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナの一覧表示</a>
   </td>
   <td>アカウント
   </td>
   <td>ストレージアカウント内のすべてのコンテナを一覧表示します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-service-properties?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobサービスのプロパティを設定する</a>
   </td>
   <td>アカウント
   </td>
   <td>ロギングとメトリックの設定を含むBlobサービスのプロパティ、およびデフォルトのサービスバージョンを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob-service-properties?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobサービスのプロパティを取得する</a>
   </td>
   <td>アカウント
   </td>
   <td>ロギングとメトリックの設定を含むBlobサービスのプロパティ、およびデフォルトのサービスバージョンを取得します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/preflight-blob-request?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">プリフライトブロブリクエスト</a>
   </td>
   <td>アカウント
   </td>
   <td>実際のリクエストを送信する前に、Blobサービスのクロスオリジンリソースシェアリング（CORS）ルールを照会します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob-service-stats?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobサービス統計を取得する</a>
   </td>
   <td>アカウント
   </td>
   <td>Blobサービスのレプリケーションに関連する統計を取得します。この操作は、ストレージアカウントで読み取りアクセス地理冗長レプリケーションが有効になっている場合にのみ、セカンダリロケーションエンドポイントで使用できます。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-account-information?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">アカウント情報を取得する</a>
   </td>
   <td>アカウント
   </td>
   <td>指定されたアカウントのSKU名とアカウントの種類を返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-user-delegation-key?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ユーザー委任キーを取得する</a>
   </td>
   <td>アカウント
   </td>
   <td>ユーザー委任SAS（共有アクセス署名）に署名するために使用できるキーを取得します。ユーザー委任SASは、Azure Active Directory（Azure AD）資格情報を使用してBlobサービスのリソースへのアクセスを許可します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/create-container?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナを作成する</a>
   </td>
   <td>容器
   </td>
   <td>ストレージアカウントに新しいコンテナを作成します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-container-properties?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナのプロパティを取得する</a>
   </td>
   <td>容器
   </td>
   <td>コンテナのすべてのユーザー定義メタデータとシステムプロパティを返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-container-metadata?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナメタデータを取得する</a>
   </td>
   <td>容器
   </td>
   <td>コンテナのユーザー定義のメタデータのみを返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-container-metadata?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナメタデータの設定</a>
   </td>
   <td>容器
   </td>
   <td>コンテナのユーザー定義のメタデータを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-container-acl?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナACLを取得する</a>
   </td>
   <td>容器
   </td>
   <td>コンテナのパブリックアクセスポリシーと保存されているアクセスポリシーを取得します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-container-acl?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナACLの設定</a>
   </td>
   <td>容器
   </td>
   <td>コンテナのパブリックアクセスポリシーと保存されているアクセスポリシーを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/lease-container?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">リースコンテナ</a>
   </td>
   <td>容器
   </td>
   <td>削除操作のためにコンテナのロックを確立および管理します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/delete-container?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コンテナを削除する</a>
   </td>
   <td>容器
   </td>
   <td>コンテナとそれに含まれるすべてのBLOBを削除します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/list-blobs?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">リストブロブ</a>
   </td>
   <td>容器
   </td>
   <td>コンテナ内のすべてのBLOBを一覧表示します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/put-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロブを置く</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>新しいblobを作成するか、コンテナー内の既存のblobを置き換えます。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobを取得する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>ユーザー定義のメタデータやシステムプロパティなど、Blobサービスからblobを読み取りまたはダウンロードします。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob-properties?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobプロパティを取得する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>BLOB上のすべてのシステムプロパティとユーザー定義のメタデータを返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-properties?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobプロパティを設定する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>既存のBLOBに対して定義されたシステムプロパティを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-expiry?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobの有効期限を設定する</a>
   </td>
   <td>ブロックブロブ
   </td>
   <td>既存のblobの有効期限を設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob-metadata?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobメタデータを取得する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>既存のBLOBまたはスナップショットのすべてのユーザー定義メタデータを取得します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-metadata?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobメタデータを設定する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>既存のBLOBのユーザー定義メタデータを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-blob-tags?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobタグを取得する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>既存のBLOBのユーザー定義タグを取得します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-tags?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobタグを設定する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>セカンダリインデックスを形成する既存のblobのユーザー定義タグを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/find-blobs-by-tags?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">タグでブロブを探す</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>ユーザー定義のタグでblobを一覧表示します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/delete-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobを削除する</a>
   </td>
   <td>ブロブをブロック、追加、ページングする
   </td>
   <td>ブロブに削除のマークを付けます。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/undelete-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobの削除を取り消す</a>
   </td>
   <td>ブロブをブロック、追加、ページングする
   </td>
   <td>ソフト削除されたBLOBおよび/または関連するすべてのソフト削除されたスナップショットのコンテンツとメタデータを復元します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/lease-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">リースブロブ</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>書き込みおよび削除操作のロックを確立および管理します。ロックされたblobを削除または書き込むには、クライアントがリースIDを提供する必要があります。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/snapshot-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">スナップショットブロブ</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>BLOBの読み取り専用スナップショットを作成します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/copy-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">Blobをコピーする</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>このストレージアカウントまたは別のストレージアカウントの宛先BLOBにソースBLOBをコピーします。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/abort-copy-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">コピーブロブを中止する</a>
   </td>
   <td>ブロブをブロック、追加、およびページングする
   </td>
   <td>保留中のCopy Blob操作を中止し、長さがゼロで完全なメタデータを持つ宛先BLOBを残します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/put-block?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロックを置く</a>
   </td>
   <td>ブロブのみをブロックする
   </td>
   <td>ブロックBLOBの一部としてコミットされる新しいブロックを作成します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/put-block-from-url?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">URLからブロックを置く</a>
   </td>
   <td>ブロブのみをブロックする
   </td>
   <td>コンテンツがURLから読み取られるブロックBLOBの一部としてコミットされる新しいブロックを作成します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/put-block-list?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロックリストを置く</a>
   </td>
   <td>ブロブのみをブロックする
   </td>
   <td>ブロックBLOBを構成するブロックIDのセットを指定することにより、BLOBをコミットします。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-block-list?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロックリストを取得</a>
   </td>
   <td>ブロブのみをブロックする
   </td>
   <td>ブロックBLOBの一部としてアップロードされたブロックのリストを取得します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/query-blob-contents?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">BLOBコンテンツのクエリ</a>
   </td>
   <td>ブロブのみをブロックする
   </td>
   <td>単純な構造化照会言語（SQL）ステートメントをBLOBのコンテンツに適用し、照会されたデータのサブセットのみを返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/set-blob-tier?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロブ層を設定する</a>
   </td>
   <td>ブロックおよびページブロブ
   </td>
   <td>ブロブのティアを設定します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/put-page?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ページを置く</a>
   </td>
   <td>ページブロブのみ
   </td>
   <td>ページの範囲をページblobに書き込みます。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/get-page-ranges?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ページ範囲を取得する</a>
   </td>
   <td>ページブロブのみ
   </td>
   <td>ページBLOBまたはページBLOBのスナップショットの有効なページ範囲のリストを返します。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/incremental-copy-blob?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">インクリメンタルコピーブロブ</a>
   </td>
   <td>ページブロブのみ
   </td>
   <td>ソースページBLOBのスナップショットを宛先ページBLOBにコピーします。差分変更のみが転送されます。
   </td>
  </tr>
  <tr>
   <td><a href="https://docs-microsoft-com.translate.goog/en-us/rest/api/storageservices/append-block?_x_tr_sl=auto&_x_tr_tl=ja&_x_tr_hl=en&_x_tr_pto=ajax,elem">ブロックを追加</a>
   </td>
   <td>ブロブのみを追加する
   </td>
   <td>データのブロックを追加BLOBの最後に書き込みます。
   </td>
  </tr>
</table>

