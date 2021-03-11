<template>
    <Layout>
       <div class="container mx-auto w-10/12">
        <div class="flex justify-around items-center">
            <h5 >Statistics: </h5>
            <div>
                Articles {{$page.allBlog.totalCount}}
            </div>
            <div>
                Tags {{$page.allTag.totalCount}}
            </div>
            <div>
                Category {{$page.allCategory.totalCount}}
            </div>
        </div>
        <h5 class="text-center">Categories:</h5>
        <div class="flex justify-around flex-wrap">
        <g-link
          v-for="edge in $page.allCategory.edges"
          :key="edge.node.id"
          :to="edge.node.path"
          class="text-s bg-transparent hover:text-blue-700 py-2 px-4 mr-3 hover:border-blue-500 border-gray-600 text-gray-700 rounded-lg my-3 border-2"
        >{{ edge.node.title }} {{edge.node.belongsTo.totalCount}} </g-link>
      </div>
        <h5 class="text-center">Tags:</h5>
        <div class="flex justify-evenly flex-wrap">
        <g-link
          v-for="edge in $page.allTag.edges"
          :key="edge.node.id"
          :to="edge.node.path"
          class="text-s bg-transparent hover:text-blue-700 py-2 px-4 mr-4 hover:border-blue-500 border-gray-600 border-2 text-gray-700 rounded-lg my-3"
        >{{ edge.node.title }} {{edge.node.belongsTo.totalCount}} </g-link>
          </div>
      </div>
    </Layout>
</template>

<page-query>
    query{
        allTag{
          totalCount
          edges{
            node{
              id
              belongsTo{
                totalCount
              }
              path
              title
            }
          }
        }
        allCategory{
          totalCount
          edges{
            node{
              id
              belongsTo{
                totalCount
              }
              path
              title
            }
          }
        }
        allBlog{
            totalCount
        }
      }
     
</page-query>

<script>
export default {
    metaInfo: {
      title: "Archive"
    },
    
   
  };
</script>